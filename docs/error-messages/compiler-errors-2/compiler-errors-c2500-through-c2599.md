---
title: Compilerfehler C2500 bis C2599
ms.date: 04/21/2019
f1_keywords:
- C2501
- C2508
- C2515
- C2519
- C2520
- C2522
- C2525
- C2527
- C2536
- C2538
- C2539
- C2546
- C2547
- C2559
- C2560
- C2564
- C2565
- C2576
- C2578
- C2580
- C2590
- C2591
- C2595
- C2596
helpviewer_keywords:
- C2501
- C2508
- C2515
- C2519
- C2520
- C2522
- C2525
- C2527
- C2536
- C2538
- C2539
- C2546
- C2547
- C2559
- C2560
- C2564
- C2565
- C2576
- C2578
- C2580
- C2590
- C2591
- C2595
- C2596
ms.assetid: a869aaed-e9f6-49e3-b273-00ea7f45bed7
ms.openlocfilehash: 87728c2d7055715b7e7d986d5ab8792ceba5c450
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64857083"
---
# <a name="compiler-errors-c2500-through-c2599"></a>Compilerfehler C2500 bis C2599

Die Artikel in diesem Abschnitt der Dokumentation wird erläutert, eine Teilmenge der Fehlermeldungen, die vom Compiler generiert werden.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>Fehlermeldungen

|Fehler|Meldung|
|-----------|-------------|
|[Compilerfehler C2500](compiler-error-C2500.md)|"*Bezeichner1*': '*Bezeichner2*' ist bereits eine direkte Basisklasse|
|Compilerfehler C2501|"*Bezeichner*": "__declspec (*Spezifizierer*)" kann nur auf Strukturen, Unions, Klassen oder unsignierte Bitfeldmember angewendet werden|
|[Compilerfehler C2502 generiert](compiler-error-C2502.md)|"*Bezeichner*": zu viele Zugriffsmodifizierer für Basisklasse|
|[Compilerfehler C2503 generiert](compiler-error-C2503.md)|"*Klasse*": Basisklasse kann keine Arrays der Größe Null enthalten|
|[Compilerfehler C2504 generiert](compiler-error-C2504.md)|"*Klasse*": Basisklasse undefiniert|
|[Compilerfehler C2505 generiert](compiler-error-C2505.md)|"*Symbol*": "__declspec (*Spezifizierer*)" kann nur auf Deklarationen oder Definitionen globaler Objekte oder statischer Datenmember angewendet werden|
|[Compilerfehler C2506 generiert](compiler-error-C2506.md)|"*Member*": "__declspec (*Spezifizierer*)" kann nicht auf dieses Symbol angewendet werden|
|[Compilerfehler C2507 generiert](compiler-error-C2507.md)|"*Bezeichner*": zu viele virtuelle Modifizierer für Basisklasse|
|Compilerfehler C2508|"*Bezeichner*": "__declspec (*spezifizierer1*)' können nicht kombiniert werden, mit" __declspec (*spezifizierer2*) "|
|[Compilerfehler C2509 generiert](compiler-error-C2509.md)|"*Bezeichner*': Member-Funktion nicht deklariert werden,"*Klasse*"|
|[Compilerfehler C2510](compiler-error-C2510.md)|"*Bezeichner*': der linken Seite von":: "muss eine Klasse/Struktur/Union sein|
|[Compilerfehler C2511 aus](compiler-error-C2511.md)|"*Bezeichner*": überladene Memberfunktion nicht gefunden "*Klasse*"|
|[Compilerfehler C2512](compiler-error-C2512.md)|"*Bezeichner*': kein geeigneter Standardkonstruktor verfügbar|
|[Compilerfehler C2513](compiler-error-C2513.md)|'*type': no variable declared before '='|
|[Compilerfehler C2514 generiert](compiler-error-C2514.md)|"*Klasse*": Klasse besitzt keine Konstruktoren|
|Compilerfehler C2515|"*Bezeichner*": "Vtguard" kann nur auf Klassendeklarationen oder Definitionen angewendet werden|
|[Compilerfehler C2516 generiert](compiler-error-C2516.md)|"*Klasse*": ist keine zulässige Basisklasse|
|[Compilerfehler C2517](compiler-error-C2517.md)|"*Bezeichner*': rechts in der '::' ist nicht definiert|
|[Compilerfehler C2518 generiert](compiler-error-C2518.md)|Schlüsselwort "*Schlüsselwort*" in der Basisklassenliste ungültig und wird ignoriert|
|Compilerfehler C2519|"*Bezeichner*": WinRT-Attribute können nur öffentliche Felder enthalten.|
|Compilerfehler C2520|"*Klasse*': kein nichtexpliziter Konstruktor für implizite Konvertierung verfügbar|
|[Compilerfehler C2521 generiert](compiler-error-C2521.md)|ein Destruktor/Finalizer ist keine Argumente akzeptiert.|
|Compilerfehler C2522|"*Bezeichner*": Bezeichner der Überladung kann nicht verwendet werden, auf "*Bezeichner1*", bereits auf angegeben ist"*Bezeichner2*"|
|[Compilerfehler C2523 generiert](compiler-error-C2523.md)|"*Klasse*:: ~*Bezeichner*": Destruktor/Finalizer-Tag stimmt nicht überein|
|[Compilerfehler C2524 generiert](compiler-error-C2524.md)|"*Bezeichner*": Destruktor/Finalizer muss eine "void"-Parameterliste haben|
|Compilerfehler C2525|"*Bezeichner*": Der Parameter "*Bezeichner1*"ist mit dem Namen"*Bezeichner2*" auf der Basis-Funktion und muss in einer veröffentlichten Implementierung übereinstimmen|
|[Compilerfehler C2526](compiler-error-C2526.md)|"*Bezeichner1*": Funktion der C-Bindung nicht zurückgeben C++ Klasse*Bezeichner2*"|
|Compilerfehler C2527|"*Bezeichner*": DefaultOverload kann nicht auf beide angegeben werden kann '*function1*'und'*Funktion2*". Entfernen Sie eine Spezifikation oder benennen Sie die Funktion während der Implementierung|
|[Compilerfehler C2528 generiert](compiler-error-C2528.md)|"*Bezeichner*': Zeiger auf Verweis ist nicht zulässig|
|[Compilerfehler C2529 generiert](compiler-error-C2529.md)|"*Bezeichner*': Verweis auf Verweis ist nicht zulässig|
|[Compilerfehler C2530 generiert](compiler-error-C2530.md)|"*Bezeichner*": Verweise müssen initialisiert werden|
|[Compilerfehler C2531 generiert](compiler-error-C2531.md)|"*Bezeichner*': Verweis auf Bitfeld ungültig|
|[Compilerfehler C2532](compiler-error-C2532.md)|"*Bezeichner*': Ungültiger Modifizierer für Verweis|
|[Compilerfehler C2533](compiler-error-C2533.md)|"*Bezeichner*': Konstruktoren, die einen Rückgabetyp nicht zulässig|
|[Compilerfehler C2534 generiert](compiler-error-C2534.md)|"*Bezeichner*": Konstruktor kann keinen Wert zurückgeben|
|[Compilerfehler C2535](compiler-error-C2535.md)|"*Bezeichner*': Memberfunktion bereits definiert oder deklariert|
|Compilerfehler C2536 generiert|Veraltet.|
|[Compilerfehler C2537 generiert](compiler-error-C2537.md)|"*Spezifizierer*": Unzulässige Angabe für Bindung|
|Compilerfehler C2538|Veraltet.|
|Compilerfehler C2539|Veraltet.|
|[Compilerfehler C2540 generiert](compiler-error-C2540.md)|nicht konstanter Ausdruck als Arraygrenze|
|[Compilerfehler C2541 generiert](compiler-error-C2541.md)|"*Bezeichner*": Objekte, die keine Zeiger sind kann nicht gelöscht werden.|
|[Compilerfehler C2542](compiler-error-C2542.md)|"*Bezeichner*": Objekt einer Klasse besitzt keinen Konstruktor zur Initialisierung|
|[Compilerfehler C2543](compiler-error-C2543.md)|erwartet ']' für den Operator "[]"|
|[Compilerfehler C2544](compiler-error-C2544.md)|erwartet ')' für '()'-Operator|
|[Compilerfehler C2545](compiler-error-C2545.md)|"*Operator*': Operator nicht gefunden, die überladen|
|Compilerfehler C2546|"*Bezeichner*": Wenn ein Typ in einer nicht-PIA, zunächst die PIA verwiesen werden muss, und eine PIA definiert ist|
|Compilerfehler C2547|"*Bezeichner*": Alle Parameter einer veröffentlichten Methode müssen in der Deklaration explizit benannt werden|
|[Compilerfehler C2548 generiert](compiler-error-C2548.md)|"*Funktion*": Fehlender Standardparameter für Parameter *Parameter*|
|[Compilerfehler C2549 generiert](compiler-error-C2549.md)|benutzerdefinierte Konvertierung kann keinen Rückgabetyp angeben.|
|[Compilerfehler C2550 generiert](compiler-error-C2550.md)|"*Bezeichner*": Initialisierungslisten für Konstruktoren dürfen nur in Konstruktordefinition stehen|
|[Compilerfehler C2551](compiler-error-C2551.md)|"void *"-Zeiger muss explizit in einen Typ umgewandelt werden|
|[Compilerfehler C2552](compiler-error-C2552.md)|"*Bezeichner*": nichtaggregate können nicht mit einer Initialisiererliste initialisiert werden|
|[Compilerfehler C2553 generiert](compiler-error-C2553.md)|"*Typ* *Derived_class*::*Funktion*': überschreibende virtuelle Funktionsrückgabetyp unterscheidet sich von"*Typ* *Base_ Klasse*::*Funktion*"|
|[Compilerfehler C2555](compiler-error-C2555.md)|"*Derived_class*::*Funktion*': überschreibende virtuelle Funktion unterscheidet sich und ist nicht über kovariante zurückgeben"*Base_class*::*Funktion*'|
|[Compilerfehler C2556 generiert](compiler-error-C2556.md)|"*type1* *Klasse*::*Funktion*": überladene Funktion unterscheidet sich nur durch den Rückgabetyp von "*Typ2* *-Klasse*::*Funktion*"|
|[Compilerfehler C2557](compiler-error-C2557.md)|"*Bezeichner*": private und geschützte Member können nicht ohne Konstruktor initialisiert werden|
|[Compilerfehler C2558](compiler-error-C2558.md)|Klasse*Klasse*': Kein Kopierkonstruktor verfügbar oder der Kopierkonstruktor 'explicit' deklariert ist|
|Compilerfehler C2559|"*Bezeichner*": kann keine Memberfunktion ohne Ref-Qualifizierer mit einer Memberfunktion mit Ref-Qualifizierer überladen|
|Compilerfehler C2560|"*Bezeichner*": kann keine Memberfunktion mit Ref-Qualifizierer mit einer Memberfunktion ohne Ref-Qualifizierer überladen|
|[Compilerfehler C2561 generiert](compiler-error-C2561.md)|"*Funktion*': Funktion muss einen Wert zurückgeben|
|[Compilerfehler C2562 generiert](compiler-error-C2562.md)|"*Funktion*": "void"-Funktion einen Wert zurückgibt|
|[Compilerfehler C2563 generiert](compiler-error-C2563.md)|nicht übereinstimmende in der Liste formaler parameter|
|Compilerfehler C2564 generiert|Veraltet.|
|Compilerfehler C2565|"*Bezeichner*": Ref-Qualifizierer ist ungültig für Konstruktor/Destruktor|
|[Compilerfehler C2566](compiler-error-C2566.md)|überladene Funktion in einem bedingten Ausdruck|
|[Compilerfehler C2567](compiler-error-C2567.md)|kann nicht geöffnet werden Metadaten in '*Filename*', *Possible_reason*|
|[Compilerfehler C2568](compiler-error-C2568.md)|"*Bezeichner*": kann nicht auf die Auflösung der funktionsüberladung|
|[Compilerfehler C2569 generiert](compiler-error-C2569.md)|"*Bezeichner*": Enumeration/Union kann nicht als Basisklasse verwendet werden|
|[Compilerfehler C2570](compiler-error-C2570.md)|"*Bezeichner*": Union kann keine Basisklasse haben.|
|[Compilerfehler C2571 generiert](compiler-error-C2571.md)|"*Bezeichner*": virtuelle Funktion darf sich nicht in Union "*Union*"|
|[Compilerfehler C2572 generiert](compiler-error-C2572.md)|"*Funktion*": Neudefinition des Standardarguments: Parameter *Anzahl*|
|[Compilerfehler C2573](compiler-error-C2573.md)|"*Klasse*': Zeiger auf Objekte dieses Typs kann nicht gelöscht werden. die Klasse verfügt über keine nicht positionierte Überladung für"Operator Delete". Verwendung: löschen oder Hinzufügen von "Operator Delete(void*)""der-Klasse|
|[Compilerfehler C2574 generiert](compiler-error-C2574.md)|"*Destruktor*": kann nicht als statisch deklariert werden|
|[Compilerfehler C2575 generiert](compiler-error-C2575.md)|"*Bezeichner*': nur Memberfunktionen und Basisklasse können virtuell sein|
|Compilerfehler C2576|"*Bezeichner*": kann nicht einführen eine neue virtuelle Methode als "Public". Markieren Sie die Methode nicht virtuell oder ändern Sie die zugriffsmöglichkeiten auf "internal" oder "protected private"|
|[Compilerfehler C2577 generiert](compiler-error-C2577.md)|"*Bezeichner*": Destruktor/Finalizer kann nicht keinen Rückgabetyp haben|
|Compilerfehler C2578|"*Klasse*': Typ kann nicht haben einen"protected"oder"protected public"-Konstruktor|
|[Compilerfehler C2579](compiler-error-C2579.md)|Typ kann nicht aufgelöst *Typ* (*Offset*). Es wird erwartet, *Dateiname*|
|Compilerfehler C2580|"*Bezeichner*": mehrere Versionen einer auf den Standardwert festgelegte spezielle Memberfunktionen sind nicht zulässig.|
|[Compilerfehler C2581 generiert](compiler-error-C2581.md)|"*Typ*": statischer "Operator =" Funktion ist nicht zulässig|
|[Compilerfehler C2582 generiert](compiler-error-C2582.md)|"Operator *Operator*"-Funktion ist in nicht verfügbar"*Typ*"|
|[Compilerfehler C2583 generiert](compiler-error-C2583.md)|"*Bezeichner*': ' Const/Volatile'"this"-Zeiger ist ungültig für Konstruktor/Destruktor|
|[Compilerfehler C2584 generiert](compiler-error-C2584.md)|"*Klasse*": direkter Basis '*base_class2*' kann nicht zugegriffen werden; bereits Basisklasse von "*base_class1*"|
|[Compilerfehler C2585](compiler-error-C2585.md)|die explizite Konvertierung in "*Typ*' ist mehrdeutig|
|[Compilerfehler C2586 generiert](compiler-error-C2586.md)|fehlerhafte benutzerdefinierte Konvertierungssyntax: Unzulässige Dereferenzierungen|
|[Compilerfehler C2587 generiert](compiler-error-C2587.md)|"*Bezeichner*": Unzulässige Verwendung der lokalen Variablen als Standardparameter|
|[Compilerfehler C2588 generiert](compiler-error-C2588.md)|":: ~*Bezeichner*": Unzulässiger globaler Destruktor/Finalizer|
|[Compilerfehler C2589 generiert](compiler-error-C2589.md)|'*Bezeichner*": Ungültiges Token auf der rechten Seite des '::'|
|Compilerfehler C2590|"*Bezeichner*': nur ein Konstruktor eine Basis-/Member-Initialisiererliste enthalten kann|
|Compilerfehler C2591|ExclusiveTo kann nicht verwendet werden kann '*Typ*"als Argument. Nur "Ref Class" ist ein gültiges argument|
|[Compilerfehler C2592](compiler-error-C2592.md)|"*Klasse*': '*base_class2*"wird geerbt von"*base_class1*' und kann nicht erneut angegeben werden|
|[Compilerfehler C2593](compiler-error-C2593.md)|' Operator *Bezeichner*' ist mehrdeutig|
|[Compilerfehler C2594 generiert](compiler-error-C2594.md)|"*Operator*": Mehrdeutige Konvertierung von '*type1*'to'*Typ2*"|
|Compilerfehler C2595|"*Bezeichner*" ein WinRT-Attributstyp muss versiegelt werden kann|
|Compilerfehler C2596|"*Bezeichner*" ein WinRT-Attributfeld kann nur "public Enum Class", "Int", "unsigned Int", "Bool", "Platform:: Type", "Platform:: String" oder "Windows:: Foundation:: HResult" sein.|
|[Compilerfehler C2597](compiler-error-C2597.md)|illegaler Verweis auf nicht statischen Member "*Bezeichner*"|
|[Compilerfehler C2598 generiert](compiler-error-C2598.md)|Verknüpfungsspezifikation muss im globalen Gültigkeitsbereich sein.|
|[Compilerfehler C2599](compiler-error-C2599.md)|"*Bezeichner*': Die Vorwärtsdeklaration einer Enumeration verwaltet/WinRT ist nicht zulässig.|

## <a name="see-also"></a>Siehe auch

[C /C++ Compiler- und Build tools, Fehler und Warnungen](../compiler-errors-1/c-cpp-build-errors.md) \
[Compilerfehler C2000 - C3999](../compiler-errors-1/compiler-errors-c2000-c3999.md)
