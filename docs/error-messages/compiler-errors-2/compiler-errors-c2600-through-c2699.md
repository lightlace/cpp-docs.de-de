---
title: Compilerfehler C2600 bis C2699
ms.date: 04/21/2019
f1_keywords:
- C2604
- C2606
- C2607
- C2608
- C2609
- C2610
- C2615
- C2618
- C2620
- C2621
- C2622
- C2623
- C2625
- C2629
- C2631
- C2639
- C2641
- C2642
- C2643
- C2644
- C2684
- C2685
- C2686
- C2697
helpviewer_keywords:
- C2604
- C2606
- C2607
- C2608
- C2609
- C2610
- C2615
- C2618
- C2620
- C2621
- C2622
- C2623
- C2625
- C2629
- C2631
- C2639
- C2641
- C2642
- C2643
- C2644
- C2684
- C2685
- C2686
- C2697
ms.assetid: 73c6319f-cbea-4a2f-913b-90dc1af61f64
ms.openlocfilehash: 9ac5f5724490574aecf0e5b542f6fdd42b0ae5bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406508"
---
# <a name="compiler-errors-c2600-through-c2699"></a>Compilerfehler C2600 bis C2699

Die Artikel in diesem Abschnitt der Dokumentation wird erläutert, eine Teilmenge der Fehlermeldungen, die vom Compiler generiert werden.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>Fehlermeldungen

|Fehler|Meldung|
|-----------|-------------|
|[Compilerfehler C2600](compiler-error-c2600.md)|"*Funktion*': eine vom Compiler generierte spezielle Memberfunktion (muss deklariert werden in der Klasse zuerst) kann nicht definiert werden.|
|[Compilerfehler C2601](compiler-error-c2601.md)|"*Funktion*": Lokale Funktionsdefinitionen sind unzulässig|
|[Compilerfehler C2602 generiert](compiler-error-c2602.md)|"*Klasse*::*Bezeichner*"ist kein Member einer Basisklasse von"*Klasse*"|
|[Compilerfehler C2603](compiler-error-c2603.md)|"*Funktion*": Zu viele statische Objekte im Blockbereich mit Konstruktoren/Destruktoren in-Funktion|
|Compilerfehler C2604|"*Bezeichner*": Kann nicht mehr als eine Schnittstellenmethode implementiert werden.|
|[Compilerfehler C2605](compiler-error-c2605.md)|"*Bezeichner*': Diese Methode ist innerhalb einer verwalteten/WinRT-Klasse reserviert|
|Compilerfehler C2606|"*class1*": kann nicht erneut implementieren "*Member*", wie es von der Common Language Runtime-Basis geerbt wurde"*Klasse2*"|
|Compilerfehler C2607|Fehler bei der statischen Assertion.|
|Compilerfehler C2608|Veraltet.|
|Compilerfehler C2609|Veraltet.|
|Compilerfehler C2610|"*Klasse*::*Member*": ist keine spezielle Memberfunktion, die der Standardwert verwendet werden kann|
|[Compilerfehler C2611 generiert](compiler-error-c2611.md)|"*token*": unzulässig nach "~" (Bezeichner)|
|[Compilerfehler C2612 generiert](compiler-error-c2612.md)|nachfolgende "*Zeichen*" in der Initialisierungsliste für Basisklasse/Elemente unzulässig.|
|[Compilerfehler C2613](compiler-error-c2613.md)|nachfolgende "*Zeichen*" in der Basisklassenliste ungültig|
|[Compilerfehler C2614](compiler-error-c2614.md)|"*Klasse*": Unzulässige elementinitialisierung: "*Bezeichner*' ist kein Basis noch Element|
|Compilerfehler C2615|Veraltet.|
|[Compilerfehler C2616](compiler-error-c2616.md)|"*Konvertierung*': kein l-kann nicht implizit konvertiert werden"*Typ1*"auf eine"*Typ2*", die sich nicht const|
|[Compilerfehler C2617 generiert](compiler-error-c2617.md)|"*Funktion*": Inkonsistente return-Anweisung|
|Compilerfehler C2618|Veraltet.|
|[Compilerfehler C2619](compiler-error-c2619.md)|"*Bezeichner*": ein statisches Datenmember ist in einer anonymen Struktur/Union nicht zulässig|
|Compilerfehler C2620|Veraltet.|
|Compilerfehler C2621|Veraltet.|
|Compilerfehler C2622 generiert|Veraltet.|
|Compilerfehler C2623 generiert|Veraltet.|
|[Compilerfehler C2624 generiert](compiler-error-c2624.md)|"*Bereich*::*Typ*": lokale Klassen können nicht zum Deklarieren von Variablen in "Extern" verwendet werden|
|Compilerfehler C2625|"*Bezeichner*': Ungültiger Unionmember; Typ"*Typ*"ist ein Verweistyp.|
|[Compilerfehler C2626](compiler-error-c2626.md)|"*Bezeichner*': ein Private/geschützte Datenmember ist in einer anonymen Struktur/Union nicht zulässig|
|[Compilerfehler C2627 generiert](compiler-error-c2627.md)|"*Funktion*': Memberfunktion ist in einer anonymen Union nicht zulässig.|
|[Compilerfehler C2628 generiert](compiler-error-c2628.md)|"*type1*"gefolgt von"*Typ2*' ist nicht zulässig (haben Sie vergessen ein ';'?)|
|Compilerfehler C2629|"*Bezeichner*": ein anonymes Struct/Union kann einen geschachtelten Typ nicht deklariert werden|
|[Compilerfehler C2630 generiert](compiler-error-c2630.md)|"*Symbol*" finden Sie in was auf eine durch Trennzeichen getrennte Liste sein soll|
|Compilerfehler C2631|"*Bezeichner*': eine Klasse oder Enumeration kann nicht in einer aliasvorlage definiert werden|
|[Compilerfehler C2632](compiler-error-c2632.md)|"*type1*"gefolgt von"*Typ2*' ist nicht zulässig|
|[Compilerfehler C2633 generiert](compiler-error-c2633.md)|"*Bezeichner*": "Inline" ist der einzig zulässige Speicherklasse für Konstruktoren|
|[Compilerfehler C2634 generiert](compiler-error-c2634.md)|"*Klasse*::*Member*': Zeiger auf Verweiselement ist nicht zulässig|
|[Compilerfehler C2635 generiert](compiler-error-c2635.md)|kann nicht konvertiert werden eine "*type1*\*' zu einer"*Typ2*\*"; Konvertierung von einer virtuellen Basisklasse wird impliziert|
|[Compilerfehler C2636 generiert](compiler-error-c2636.md)|"*Bezeichner*': Zeiger auf Verweiselement ist nicht zulässig|
|[Compilerfehler C2637 generiert](compiler-error-c2637.md)|"*Bezeichner*': Zeiger auf Datenmember kann nicht geändert werden.|
|[Compilerfehler C2638 generiert](compiler-error-c2638.md)|"*Bezeichner*": __based-Modifizierer für Zeiger auf Member unzulässig|
|Compilerfehler C2639|Veraltet.|
|[Compilerfehler C2640 generiert](compiler-error-c2640.md)|"*Bezeichner*": __based-Modifizierer auf Verweis unzulässig|
|Compilerfehler C2641|Veraltet.|
|Compilerfehler C2642|Veraltet.|
|Compilerfehler C2643|Veraltet.|
|Compilerfehler C2644|Veraltet.|
|[Compilerfehler C2645 generiert](compiler-error-c2645.md)|kein vollständiger Name für Elementzeiger (gefunden ":: *")|
|[Compilerfehler C2646](compiler-error-c2646.md)|ein anonymes Struct/Union im globalen oder im Namespacebereich muss als statisch deklariert werden|
|[Compilerfehler C2647 generiert](compiler-error-c2647.md)|"*Operator*": kann nicht dereferenziert werden eine "*type1*" auf eine "*Typ2*"|
|[Compilerfehler C2648 generiert](compiler-error-c2648.md)|"*Bezeichner*": Verwenden von Elementen als Standardparameter statische Elemente erfordert|
|[Compilerfehler C2649](compiler-error-c2649.md)|"*Bezeichner*": ist es sich nicht um eine "Klasse/Struktur/Union"|
|[Compilerfehler C2650 generiert](compiler-error-c2650.md)|"*Operator*': eine virtuelle Funktion nicht möglich|
|[Compilerfehler C2651](compiler-error-c2651.md)|"*Typ*': der linken Seite von":: "muss eine Klasse, Struktur oder Union sein|
|[Compilerfehler C2652](compiler-error-c2652.md)|"*Bezeichner*": Unzulässiger Kopierkonstruktor: erster Parameter darf nicht sein. ein '*Typ*"|
|[Compilerfehler C2653](compiler-error-c2653.md)|"*Bezeichner*": ist kein Name für eine Klasse oder Namespace|
|[Compilerfehler C2654](compiler-error-c2654.md)|"*Bezeichner*": Zugriff auf Element außerhalb einer Methode|
|[Compilerfehler C2655 generiert](compiler-error-c2655.md)|"*Bezeichner*': Definition oder Neudeklaration im aktuellen Gültigkeitsbereich unzulässig|
|[Compilerfehler C2656](compiler-error-c2656.md)|"*Funktion*': Funktion als Bitfeld nicht zulässig.|
|[Compilerfehler C2657 generiert](compiler-error-c2657.md)|"*Klasse*:: *" zu Beginn einer Anweisung gefunden (fehlt die Typangabe?)|
|[Compilerfehler C2658 generiert](compiler-error-c2658.md)|"*Bezeichner*": Neudefinition in anonymes Struct/Union|
|[Compilerfehler C2659](compiler-error-c2659.md)|"*Operator*': Funktion als Linker Operand|
|[Compilerfehler C2660](compiler-error-c2660.md)|"*Funktion*': Funktion akzeptiert keine *Anzahl* Argumente|
|[Compilerfehler C2661 generiert](compiler-error-c2661.md)|"*Funktion*": keine überladene Funktion akzeptiert *Anzahl* Argumente|
|[Compilerfehler C2662 generiert](compiler-error-c2662.md)|"*Funktion*": "this"-Zeiger aus kann nicht konvertiert werden kann '*type1*'to'*Typ2*"|
|[Compilerfehler C2663 generiert](compiler-error-c2663.md)|"*Funktion*': *Anzahl* Überladung(en) gibt es keine zulässige Konvertierung für"this"-Zeiger|
|[Compilerfehler C2664 auftritt](compiler-error-c2664.md)|"*Funktion*": Konvertierung von Argument kann nicht *Anzahl* aus "*Typ1*'to'*Typ2*"|
|[Compilerfehler C2665](compiler-error-c2665.md)|"*Funktion*': keines der *Anzahl* Überladungen konnten alle Argumenttypen konvertiert|
|[Compilerfehler C2666](compiler-error-c2666.md)|"*Funktion*': *Anzahl* Überladungen haben ähnliche Konvertierungen|
|[Compilerfehler C2667](compiler-error-c2667.md)|"*Funktion*': keiner der *Anzahl* Überladungen haben beste Konvertierung|
|[Compilerfehler C2668](compiler-error-c2668.md)|"*Funktion*': Mehrdeutiger Aufruf einer überladenen Funktion|
|[Compilerfehler C2669 generiert](compiler-error-c2669.md)|Member-Funktion, die in einer anonymen Union nicht zulässig.|
|[Compilerfehler C2670](compiler-error-c2670.md)|"*Funktion*': die Funktionsvorlage kann Parameter konvertieren *Anzahl* vom Typ"*Typ*"|
|[Compilerfehler C2671 generiert](compiler-error-c2671.md)|"*Funktion*": statische Memberfunktionen keinen this-Zeiger|
|[Compilerfehler C2672](compiler-error-c2672.md)|"*Funktion*": keine übereinstimmende überladene Funktion gefunden.|
|[Compilerfehler C2673 generiert](compiler-error-c2673.md)|"*Funktion*': globale Funktionen haben keinen this-Zeiger|
|[Compilerfehler C2674](compiler-error-c2674.md)|eine generische Deklaration ist in diesem Kontext nicht zulässig.|
|[Compilerfehler C2675](compiler-error-c2675.md)|unäre "*Operator*': '*Typ*" definiert diesen Operator oder eine Konvertierung in einen geeigneten Typ nicht für den vordefinierten Operator|
|[Compilerfehler C2676](compiler-error-c2676.md)|binäres '*Operator*': '*Typ*"definiert diesen Operator oder eine Konvertierung in einen geeigneten Typ nicht für den vordefinierten Operator|
|[Compilerfehler C2677 generiert](compiler-error-c2677.md)|binäre "*Operator*': Es konnte kein globaler Operator gefunden werden, der Typ akzeptiert"*Typ*"(oder es ist keine geeignete Konvertierung)|
|[Compilerfehler C2678](compiler-error-c2678.md)|binäres '*Operator*": Es konnte kein Operator gefunden werden, der einen linksseitigen Operanden vom Typ akzeptiert"*Typ*"(oder es ist keine geeignete Konvertierung)|
|[Compilerfehler C2679 generiert](compiler-error-c2679.md)|binäres '*Operator*": Es konnte kein Operator gefunden werden, der einen rechtsseitigen Operanden vom Typ akzeptiert"*Typ*"(oder es ist keine geeignete Konvertierung)|
|[Compilerfehler C2680](compiler-error-c2680.md)|"*Typ*': Ungültiger Zieltyp für *Umwandlung*|
|[Compilerfehler C2681 generiert](compiler-error-c2681.md)|"*Typ*': Ungültiger Ausdruckstyp für *Umwandlung*|
|[Compilerfehler C2682 generiert](compiler-error-c2682.md)|kann nicht verwendet '*Umwandlung*"zum Konvertieren von"*type1*'to'*Typ2*"|
|[Compilerfehler C2683 generiert](compiler-error-c2683.md)|"*Umwandlung*': '*Typ*' ist kein polymorpher Typ|
|Compilerfehler C2684|"*Deklarator*": gelöschte und Standardfunktionen werden in verwalteten/WinRT-Klassen nicht unterstützt.|
|Compilerfehler C2685|"*Deklarator*": gelöschte und Standardfunktionen werden mit expliziten einschränkungsspezifizierern nicht unterstützt.|
|Compilerfehler C2686|statische und nicht statische Memberfunktionen können nicht mit denselben Parametertypen überladen werden.|
|[Compilerfehler C2687 generiert](compiler-error-c2687.md)|"*Typ*": Exception-Deklaration kann nicht "void" sein oder einen unvollständigen Typ oder Zeiger oder Verweis auf einen unvollständigen Typ zu kennzeichnen|
|[Compilerfehler C2688](compiler-error-c2688.md)|"*Typ*::*Member*": covariant-Rückgaben mit mehrfacher oder virtueller Vererbung werden für Varargs-Funktionen nicht unterstützt.|
|[Compilerfehler C2689 generiert](compiler-error-c2689.md)|"*Funktion*': eine Friend-Funktion kann nicht innerhalb einer lokalen Klasse definiert werden|
|[Compilerfehler C2690](compiler-error-c2690.md)|"*Operator*': Zeigerarithmetik kann nicht auf einem verwalteten/WinRT-Array|
|[Compilerfehler C2691](compiler-error-c2691.md)|"*Typ*": ein verwaltet/WinRT-Array darf nicht diesen Elementtyp aufweisen|
|[Compilerfehler C2692](compiler-error-c2692.md)|"*Funktion*': vollständige Funktionen mit Prototyp erforderlich sind, im C-Compiler mit der" / Clr "Option|
|[Compilerfehler C2693](compiler-error-c2693.md)|"*Operator*": Unzulässiger Vergleich für Verweise auf verwaltete/WinRT-Array|
|[Compilerfehler C2694 generiert](compiler-error-c2694.md)|"*Überschreibungsfunktion*": Überschreiben der virtuellen Funktion hat weniger restriktive Ausnahmespezifikation als virtuelle Basisklasse-Memberfunktion "*Basisfunktion*"|
|[Compilerfehler C2695 generiert](compiler-error-c2695.md)|"*Überschreibungsfunktion*": Überschreiben der virtuellen Funktion unterscheidet sich von "*Basisfunktion*" nur durch die Aufrufkonvention|
|[Compilerfehler C2696](compiler-error-c2696.md)|Ein temporäres Objekt des verwalteten/WinRT-Typ kann nicht erstellt werden kann '*Typ*"|
|Compilerfehler C2697|Veraltet.|
|[Compilerfehler C2698 generiert](compiler-error-c2698.md)|Die using-Deklaration für "*Deklaration1*"kann nicht gleichzeitig vorhanden sein mit den vorhandenen using-Deklaration für"*Deklaration2*"|

## <a name="see-also"></a>Siehe auch

[C /C++ Compiler- und Build tools, Fehler und Warnungen](../compiler-errors-1/c-cpp-build-errors.md) \
[Compilerfehler C2000 - C3999](../compiler-errors-1/compiler-errors-c2000-c3999.md)
