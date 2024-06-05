# Ovládání RGB LED pomocí IR Dálkového Ovladače

Tento Arduino projekt vám umožní ovládat barvu a intenzitu RGB LED pomocí IR dálkového ovladače. Používáme knihovnu `IRremote` pro příjem IR signálů a úpravu LED na základě těchto vstupů.

## Komponenty
- Arduino deska (např. Arduino Uno)
- RGB LED
- IR přijímač
- IR dálkový ovladač
- Rezistory (vhodné hodnoty pro vaši RGB LED)
- Prototypovací deska (breadboard) a propojovací vodiče

## Zapojení
1. **IR Přijímač:**
   - Připojte IR přijímač k digitálnímu pinu 12 na Arduinu.
   - Připojte VCC k 5V a GND k zemi.

2. **RGB LED:**
   - Připojte piny pro červenou, zelenou a modrou barvu RGB LED k pinům Arduina s PWM (např. 10, 6 a 9).
   - Připojte společnou katodu (nebo anodu, podle typu vaší LED) k zemi (nebo k 5V pro společnou anodu).
   - Použijte vhodné rezistory pro každý barevný pin.

## Vysvětlení Kódu

### Knihovny a Definice Pinů
Používáme knihovnu `IRremote` pro příjem signálů z IR dálkového ovladače a definujeme piny pro RGB LED.

### Funkce Setup
Funkce `setup()` inicializuje IR přijímač a sériovou komunikaci. Také nastaví piny RGB LED jako výstupní.

### Funkce Light Up
Funkce `lightUp()` nastaví intenzitu dané barvy.

### Hlavní Smyčka
Funkce `loop()` kontroluje příchozí IR signály a zpracovává je.

### Funkce Přijetí Čísla
Funkce `recievedNum()` převádí IR kódy na odpovídající číslice.

## Pokyny k Použití
1. **Zapojení:**
   - Připojte IR přijímač a RGB LED k Arduinu podle výše uvedeného schématu zapojení.
   - Nahrajte poskytnutý kód do Arduina.

2. **Ovládání:**
   - Použijte IR dálkový ovladač k odeslání signálů do IR přijímače.
   - Zadejte požadovanou hodnotu intenzity pomocí dálkového ovladače (číslice 1-9).
   - Stiskněte tlačítko "Enter" na dálkovém ovladači pro potvrzení intenzity.
   - Vyberte požadovanou barvu stisknutím příslušného tlačítka pro zelenou, modrou nebo červenou.
   - LED se rozsvítí zvolenou barvou a intenzitou.

3. **Poznámky:**
   - Ujistěte se, že kódy dálkového ovladače odpovídají těm, které jsou definované v kódu. Pokud ne, upravte je podle kódů vašeho ovladače.
   - Pokud hodnota intenzity přesáhne 255, bude omezena na 255, aby se předešlo přetečení.

Dodržováním těchto pokynů můžete ovládat barvu a jas RGB LED pomocí IR dálkového ovladače a Arduina.
