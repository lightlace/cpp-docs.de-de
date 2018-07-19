---
title: Compilerwarnungen C4600 durch C4799 | Microsoft-Dokumentation
ms.date: 07/03/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4602
- C4603
- C4609
- C4612
- C4613
- C4620
- C4622
- C4629
- C4631
- C4634
- C4635
- C4636
- C4637
- C4638
- C4645
- C4646
- C4655
- C4657
- C4658
- C4662
- C4670
- C4671
- C4672
- C4674
- C4676
- C4678
- C4681
- C4682
- C4685
- C4689
- C4693
- C4694
- C4695
- C4696
- C4718
- C4719
- C4720
- C4721
- C4722
- C4724
- C4725
- C4728
- C4729
- C4732
- C4739
- C4750
- C4751
- C4752
- C4754
- C4755
- C4757
- C4764
- C4767
- C4770
- C4792
- C4794
dev_langs:
- C++
ms.assetid: 22bd4392-f3be-445c-9f23-6126aebac901
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f25e0f42383aa993cd0d3f0190eed768fe39359
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37854043"
---
# <a name="compiler-warnings-c4600-through-c4799"></a>Compilerwarnungen C4600 durch C4799

Die Artikel in diesem Abschnitt der Dokumentation wird erläutert, eine Teilmenge der die Warnmeldungen an, die vom Compiler generiert werden.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="warning-messages"></a>Warnmeldungen

|Warnung|Meldung|
|-------------|-------------|
|[Compilerwarnung (Ebene 1) C4600](../../error-messages/compiler-warnings/compiler-warning-level-1-c4600.md)|#pragma 'Makroname': eine gültige nicht leere Zeichenfolge erwartet|
|Compilerwarnung (Stufe 1) C4602|#pragma Pop_macro: 'Makroname' kein vorherigen #pragma Push_macro für diesen Bezeichner|
|Compilerwarnung (Stufe 1) C4603|"*Bezeichner*": Makro ist nicht definiert oder die Definition wurde nach Verwendung des vorkompilierten Headers|
|Compilerwarnung (Stufe 1) C4604|"*Typ*': Übergabe eines Arguments nach Wert zwischen nativen und verwalteten Grenze erfordert einen gültigen Kopierkonstruktor. Andernfalls ist das Laufzeitverhalten nicht definiert|
|Compilerwarnung (Stufe 1) C4605|' / D*Makro*"in der aktuellen Befehlszeile angegeben, jedoch wurde nicht angegeben, wenn die vorkompilierter Header erstellt wurde|
|[Compilerwarnung (Ebene 1) C4606](../../error-messages/compiler-warnings/compiler-warning-level-1-c4606.md)|#pragma-Warnung: "Warnungsnummer" ignoriert. Codeanalysewarnungen sind keinen Warnstufen zugeordnet|
|[Compilerwarnung (Ebene 3) C4608](../../error-messages/compiler-warnings/compiler-warning-level-3-c4608.md)|"union_member" wurde bereits von einem anderen Union-Member in der Initialisierungsliste initialisiert, "union_member"|
|Compilerwarnung (Stufe 3, Fehler) C4609|"*type1*"abgeleitet von Standardschnittstelle"*Schnittstelle*'für Typ"*Typ2*". Verwenden Sie eine andere Standardschnittstelle für "*type1*", oder unterteilen Sie die basisbeziehung/abgeleitete Beziehung.|
|[Compilerwarnung (Ebene 4) C4610](../../error-messages/compiler-warnings/compiler-warning-level-4-c4610.md)|'Klasse'-Objekt kann nicht instanziiert werden - benutzerdefinierter Konstruktor erforderlich|
|[Compilerwarnung (Ebene 4) C4611](../../error-messages/compiler-warnings/compiler-warning-level-4-c4611.md)|Interaktion zwischen "Function" und C++-objektlöschung ist nicht portabel|
|Compilerwarnung (Stufe 1) C4612|Fehler im Namen der Includedatei|
|Compilerwarnung (Stufe 1) C4613|"*Symbol*": Klasse des Segments kann nicht geändert werden|
|[Compilerwarnung (Ebene 1) C4615](../../error-messages/compiler-warnings/compiler-warning-level-1-c4615.md)|#pragma-Warnung: Unbekannter Typ der benutzerwarnung|
|[Compilerwarnung (Ebene 1) C4616](../../error-messages/compiler-warnings/compiler-warning-level-1-c4616.md)|#pragma-Warnung: Warnungsnummer 'number' keine gültige compilerwarnung|
|[Compilerwarnung (Ebene 1) C4618](../../error-messages/compiler-warnings/compiler-warning-level-1-c4618.md)|Pragma-Parameter enthalten eine leere Zeichenfolge; Pragma wird ignoriert|
|[Compilerwarnung (Ebene 3) C4619](../../error-messages/compiler-warnings/compiler-warning-level-3-c4619.md)|#pragma-Warnung: Keine Warnungsnummer 'number' vorhanden|
|Compilerwarnung (Stufe 1) C4620|Keine Postfix-Form von 'Operator ++' für den Typ 'Typ' gefunden, Präfix-Form verwendet|
|[Compilerwarnung (Ebene 1) C4621](../../error-messages/compiler-warnings/compiler-warning-level-1-c4621.md)|keine Postfix-Form des Operators"--" für Typ 'Typ', Präfix-Form gefunden.|
|Compilerwarnung (Stufe 3) C4622|Überschreiben der Debuginformationen gebildet, bei der Erstellung der vorkompilierten Headerdatei in Objektdatei: "Datei"|
|[Compilerwarnung (Ebene 4) C4623](../../error-messages/compiler-warnings/compiler-warning-level-4-c4623.md)|'abgeleitete Klasse': Standardkonstruktor wurde implizit als gelöscht, weil ein Basisklasse-Standardkonstruktor nicht zugegriffen werden kann oder gelöschten ist definiert.|
|[Compilerwarnung (Ebene 1) C4624](../../error-messages/compiler-warnings/compiler-warning-level-1-c4624.md)|'abgeleitete Klasse': Destruktor wurde implizit als gelöscht, da ein Basisklassen-Destruktor nicht zugegriffen werden kann oder gelöschten ist definiert.|
|[Compilerwarnung (Ebene 4) C4625](../../error-messages/compiler-warnings/compiler-warning-level-4-c4625.md)|'abgeleitete Klasse': Kopierkonstruktor wurde implizit als gelöscht, weil ein Kopierkonstruktor Basisklasse nicht zugegriffen werden kann oder gelöschten definiert.|
|[Compilerwarnung (Ebene 4) C4626](../../error-messages/compiler-warnings/compiler-warning-level-4-c4626.md)|'abgeleitete Klasse': Zuweisungsoperator wurde implizit als gelöscht definiert, da ein Basisklasse-Zuweisungsoperator nicht zugegriffen werden kann oder gelöscht wird|
|[Compilerwarnung (Ebene 1) C4627](../../error-messages/compiler-warnings/compiler-warning-level-1-c4627.md)|"\<Bezeichner >': wird bei der Suche nach Verwendung des vorkompilierten Headers übersprungen|
|[Compilerwarnung (Ebene 1) C4628](../../error-messages/compiler-warnings/compiler-warning-level-1-c4628.md)|'digraphs' werden mit '-Ze' nicht unterstützt. Die Zeichensequenz 'Digraph' wird nicht als alternatives Token für "%s" interpretiert.|
|Compilerwarnung (Stufe 4) C4629|"Digraph" wurde verwendet, Zeichensequenz "Digraph" wurde als Token "Zeichen" interpretiert (Fügen Sie zwischen den beiden Zeichen ein Leerzeichen ein, wenn Sie etwas anderes beabsichtigt haben)|
|[Compilerwarnung (Ebene 1) C4630](../../error-messages/compiler-warnings/compiler-warning-level-1-c4630.md)|'Symbol': Speicherklassenspezifizierer "Extern" nicht für Elementdefinition|
|Compilerwarnung (Stufe 2) C4631|MSXML oder XPath ist nicht verfügbar. XML-Dokumentkommentare werden nicht verarbeitet. reason|
|[Compilerwarnung (Ebene 1) C4632](../../error-messages/compiler-warnings/compiler-warning-level-1-c4632.md)|Der XML-Dokumentkommentar: Datei - Zugriff verweigert: Grund|
|[Compilerwarnung (Ebene 3) C4633](../../error-messages/compiler-warnings/compiler-warning-level-3-c4633.md)|XML-dokumentkommentarziel: Fehler: Grund|
|Compilerwarnung (Stufe 4) C4634|XML-dokumentkommentarziel: kann nicht angewendet werden: Grund|
|Compilerwarnung (Stufe 3) C4635|XML-Dokumentkommentarziel: Ungültige XML: Grund|
|Compilerwarnung (Stufe 3) C4636|Angewendeter zum Erstellen von XML-Dokumentkommentar: Tag ist nicht leer 'Attribut' Attribut erforderlich.|
|Compilerwarnung (Ebene 3 und Ebene 4) C4637|XML-dokumentkommentarziel: \<enthalten >-Tag wurde verworfen. Grund|
|Compilerwarnung (Stufe 3) C4638|XML-dokumentkommentarziel: Verweis auf unbekanntes Symbol 'Symbol'.|
|[Compilerwarnung (Ebene 4) C4639](../../error-messages/compiler-warnings/compiler-warning-level-4-c4639.md)|MSXML-Fehler: XML-Dokument, das Kommentare nicht verarbeitet werden. Grund|
|[Compilerwarnung (Ebene 3) C4640](../../error-messages/compiler-warnings/compiler-warning-level-3-c4640.md)|„Instanz“: Erstellen eines lokalen static-Objekts ist nicht threadsicher|
|[Compilerwarnung (Ebene 3) C4641](../../error-messages/compiler-warnings/compiler-warning-level-3-c4641.md)|XML-Dokumentkommentar enthält einen mehrdeutigen Querverweis:|
|Compilerwarnung (Stufe 3) C4645|Eine Funktion, die mit "__declspec(noreturn)" deklariert wurde, hat eine Rückgabeanweisung|
|Compilerwarnung (Stufe 3) C4646|Eine Funktion, die mit "__declspec(noreturn)" deklariert wurde, hat einen nicht leeren Rückgabetyp|
|Compilerwarnung (Stufe 3) C4647|Verändertes Programmverhalten: __is_pod (*Typ*) verfügt über unterschiedliche Wert in früheren Versionen|
|Compilerwarnung (Stufe 3) C4648|das Standardattribut "Carries_dependency" wird ignoriert.|
|Compilerwarnung (Stufe 3) C4649|Attribute werden in diesem Kontext ignoriert.|
|[Compilerwarnung (Ebene 1) C4650](../../error-messages/compiler-warnings/compiler-warning-level-1-c4650.md)|die Debuginformationen nicht in vorkompilierter Headerdatei vorhanden; nur globale Symbole aus dieser Datei werden verfügbar sein.|
|[Compilerwarnung (Ebene 1) C4651](../../error-messages/compiler-warnings/compiler-warning-level-1-c4651.md)|"Definition" für vorkompilierte Header, aber nicht für aktuelle Kompilierung angegeben|
|[Compilerwarnung (Ebene 1) C4652](../../error-messages/compiler-warnings/compiler-warning-level-1-c4652.md)|die Compileroption "Option" inkonsistent mit der vorkompilierten Headerdatei; aktuelle Befehlszeilenoption überschreibt, die in der vorkompilierten Headerdatei definiert|
|[Compilerwarnung (Ebene 2) C4653](../../error-messages/compiler-warnings/compiler-warning-level-2-c4653.md)|die Compileroption "Option" inkonsistent mit der vorkompilierten Headerdatei; aktuelle Befehlszeilenoption wird ignoriert|
|Compilerwarnung (Stufe 4) C4654|Einschließen von Code, die vor platziert der vorkompilierten Headerdatei wird, wird ignoriert. Fügen Sie dem vorkompilierten Header Code hinzu.|
|Compilerwarnung (Stufe 1) C4655|'Symbol': Variablentyp ist neuer als beim letzten Build oder wurde an anderer Stelle unterschiedlich definiert|
|[Compilerwarnung (Ebene 1) C4656](../../error-messages/compiler-warnings/compiler-warning-level-1-c4656.md)|'Symbol': Datentyp ist neu oder seit dem letzten Build geändert wurde oder wird an anderer Stelle unterschiedlich definiert|
|Compilerwarnung (Stufe 1) C4657|der Ausdruck bezieht einen Datentyp, der seit dem letzten Build neu hinzugekommen ist|
|Compilerwarnung (Stufe 1) C4658|'Funktion': Funktionsprototyp ist neuer als beim letzten Build oder wurde an anderer Stelle unterschiedlich deklariert|
|[Compilerwarnung (Ebene 1) C4659](../../error-messages/compiler-warnings/compiler-warning-level-1-c4659.md)|#pragma "Pragma": Gebrauch des reservierten Segments "Segment" hat ein undefiniertes Verhalten, verwenden Sie #pragma Comment (Linker,...)|
|[Compilerwarnung (Ebene 1) C4661](../../error-messages/compiler-warnings/compiler-warning-level-1-c4661.md)|'Bezeichner': keine geeignete Definition für explizite Anforderung der Vorlageninstanziierung angegeben|
|Compilerwarnung (Stufe 1) C4662|Explizite Instanziierung; Vorlagenklasse "Bezeichner1" besitzt keine Definition, von der "Bezeichner2" spezialisiert werden kann.|
|[Compilerwarnung (Ebene 1) C4667](../../error-messages/compiler-warnings/compiler-warning-level-1-c4667.md)|'Funktion': keine Funktionsvorlage definiert, die entspricht der erforderlichen Instanziierung|
|[Compilerwarnung (Ebene 4) C4668](../../error-messages/compiler-warnings/compiler-warning-level-4-c4668.md)|'Symbol' ist als ein Präprozessormakro, und Ersetzen Sie dabei mit '0' für 'Direktive' nicht definiert.|
|[Compilerwarnung (Ebene 1) C4669](../../error-messages/compiler-warnings/compiler-warning-level-1-c4669.md)|'cast': unsichere Konvertierung: "Klasse" ist ein verwalteter Typ-Objekt|
|Compilerwarnung (Stufe 4) C4670|'Bezeichner': Diese Basisklasse ist nicht möglich|
|Compilerwarnung (Stufe 4) C4671|'Bezeichner': der Kopierkonstruktor ist nicht möglich.|
|Compilerwarnung (Stufe 4) C4672|'Bezeichner1': mehrdeutig. Zuerst als 'identifier2' aufgetreten|
|[Compilerwarnung (Ebene 4) C4673](../../error-messages/compiler-warnings/compiler-warning-level-4-c4673.md)|Auslösen von "Bezeichner" die folgenden Typen werden nicht an die Catch-Standort betrachtet werden|
|Compilerwarnung (Stufe 1) C4674|"Methode" sollte als "static" deklariert werden und nur einen Parameter haben|
|Compilerwarnung (Stufe 4) C4676|"%s": der Destruktor ist nicht möglich.|
|[Compilerwarnung (Ebene 1) C4677](../../error-messages/compiler-warnings/compiler-warning-level-1-c4677.md)|'Funktion': die Signatur des nicht privaten Members enthält den privaten Assemblytyp 'Private_type'|
|Compilerwarnung (Stufe 1) C4678|Die Basisklasse 'base_type' hat eine stärkere Zugriffsbeschränkung als 'derived_type'|
|[Compilerwarnung (Ebene 1) C4679](../../error-messages/compiler-warnings/compiler-warning-level-1-c4679.md)|'Member': Member konnte nicht importiert|
|[Compilerwarnung (Ebene 4) C4680](../../error-messages/compiler-warnings/compiler-warning-level-4-c4680.md)|'Klasse': Co-Klasse gibt eine Standardschnittstelle keine|
|Compilerwarnung (Stufe 4) C4681|'Klasse': Co-Klasse gibt eine Standardschnittstelle, die eine Ereignisquelle ist keine|
|Compilerwarnung (Stufe 4) C4682|'Parameter': kein direktionales Parameterattribut angegeben, Standardwert [in]|
|[Compilerwarnung (Ebene 1) C4683](../../error-messages/compiler-warnings/compiler-warning-level-1-c4683.md)|'Funktion': Ereignisquelle hat einen "Out"-Parameter enthalten. Seien Sie vorsichtig, wenn mehrere Ereignishandler eine Hookfunktion erstellen|
|[Compilerwarnung (Ebene 1) C4684](../../error-messages/compiler-warnings/compiler-warning-level-1-c4684.md)|'Attribut': Warnung!! Attribut kann zu Ungültiger codegenerierung führen: Verwenden Sie mit Vorsicht|
|Compilerwarnung (Stufe 1) C4685|"> >" erwartet. ">>" wurde beim Verarbeiten der Vorlagenparameter gefunden|
|[Compilerwarnung (Ebene 3) C4686](../../error-messages/compiler-warnings/compiler-warning-level-3-c4686.md)|„benutzerdefinierter Typ“: mögliche Verhaltensänderung, Änderung in der UDT gibt Aufrufkonvention zurück|
|[Compilerwarnung C4687 (Fehler)](../../error-messages/compiler-warnings/compiler-warning-c4687.md)|'Klasse': eine versiegelte abstrakte Klasse kann eine Schnittstelle "Schnittstelle" nicht implementieren|
|[Compilerwarnung (Stufe 1) C4688](../../error-messages/compiler-warnings/compiler-warning-level-1-c4688.md)|"constraint": Die Einschränkungsliste enthält den privaten Assemblytyp "type".|
|Compilerwarnung (Stufe 1) C4689|"%c": nicht unterstütztes Zeichen in #pragma Detect_mismatch; #pragma ignoriert|
|[Compilerwarnung (Stufe 4) C4690](../../error-messages/compiler-warnings/compiler-warning-level-4-c4690.md)|\[ Emitidl (Pop)]: mehr POP-als Push-Vorgänge|
|[Compilerwarnung (Ebene 1) C4691](../../error-messages/compiler-warnings/compiler-warning-level-1-c4691.md)|'Typ': Typ verwiesen wurde erwartet, in der nicht referenzierte Assembly "File", Typ, der in der aktuellen Übersetzungseinheit, die stattdessen verwendet|
|[Compilerwarnung (Ebene 1) C4692](../../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md)|'Funktion': Die Signatur des nicht privaten Members enthält den privaten systemeigenen Assemblytyp 'systemeigener_Typ'|
|[Compilerwarnung (Ebene 1, Fehler) C4693](../../error-messages/compiler-warnings/compiler-warning-c4693.md)|'Klasse': eine versiegelte abstrakte Klasse kann nicht einer beliebigen Instanz Instanz Member 'Member' haben|
|[Compilerwarnung (Ebene 1, Fehler) C4694](../../error-messages/compiler-warnings/compiler-warning-c4694.md)|'Klasse': eine versiegelte abstrakte Klasse kann keine Basisklasse 'basis_klasse' aufweisen|
|Compilerwarnung (Stufe 1) C4695|#pragma Execution_character_set: "Zeichensatz" ist kein unterstütztes Argument: derzeit wird nur "UTF-8" wird unterstützt.|
|Compilerwarnung (Stufe 1) C4696|/ ZBvalue1-Option erstellt außerhalb des gültigen Bereichs. Wenn "value2"|
|[Compilerwarnung (Ebene 1 und Ebene 4) C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md)|nicht initialisierte lokale Variable "Name" verwendet|
|[Compilerwarnung (Ebene 4) C4701](../../error-messages/compiler-warnings/compiler-warning-level-4-c4701.md)|möglicherweise nicht initialisierte lokale Variable "Name" verwendet|
|[Compilerwarnung (Ebene 4) C4702](../../error-messages/compiler-warnings/compiler-warning-level-4-c4702.md)|unerreichbarer code|
|[Compilerwarnung (Ebene 4) C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)|möglicherweise nicht initialisierte lokale Zeigervariable "%s" verwendet|
|[Compilerwarnung (Ebene 4) C4706](../../error-messages/compiler-warnings/compiler-warning-level-4-c4706.md)|Zuweisung in bedingtem Ausdruck|
|[Compilerwarnung (Ebene 4) C4709](../../error-messages/compiler-warnings/compiler-warning-level-4-c4709.md)|Kommaoperator innerhalb eines Feldindex-Ausdrucks|
|[Compilerwarnung (Ebene 4) C4710](../../error-messages/compiler-warnings/compiler-warning-level-4-c4710.md)|'Funktion': Funktion ist nicht inline|
|[Compilerwarnung (Ebene 1) C4711](../../error-messages/compiler-warnings/compiler-warning-level-1-c4711.md)|' Funktion ' für die automatische Inlineerweiterung ausgewählt|
|[Compilerwarnung (Ebene 4) C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md)|'Funktion' als __forceinline markierte nicht inline|
|[Compilerwarnung (Ebene 1) C4715](../../error-messages/compiler-warnings/compiler-warning-level-1-c4715.md)|'Funktion': nicht alle Codepfade geben einen Wert zurück.|
|[Compilerwarnung (Ebene 1, Fehler) C4716](../../error-messages/compiler-warnings/compiler-warning-level-1-c4716.md)|'Funktion': muss einen Wert zurückgeben|
|[Compilerwarnung (Ebene 1) C4717](../../error-messages/compiler-warnings/compiler-warning-level-1-c4717.md)|"Function": rekursiv für alle Steuerelementpfade, die Funktion verursacht einen Stapelüberlauf zur Laufzeit|
|Compilerwarnung (Stufe 4) C4718|'Funktionsaufruf': rekursiver Aufruf besitzt keine Nebeneffekte, wird gelöscht|
|Compilerwarnung (Stufe 1) C4719|Doppelte Konstante gefunden wird, wenn Qfast angegeben – verwenden Sie "f" als Suffix mit einfacher Genauigkeit an.|
|Compilerwarnung (Stufe 2) C4720|Inline-Inlineassembler meldet: "Meldung"|
|Compilerwarnung (Stufe 1) C4721|'Funktion': nicht als systeminterne Funktion verfügbar|
|Compilerwarnung (Stufe 1) C4722|"Function": Destruktor gibt nie Werte zurück, mögliche Speicherverluste|
|[Compilerwarnung (Ebene 3) C4723](../../error-messages/compiler-warnings/compiler-warning-level-3-c4723.md)|Mögliche Division durch 0|
|Compilerwarnung (Stufe 3) C4724|Mögliches Modulo durch 0 (Null)|
|Compilerwarnung (Stufe 3) C4725|Anweisung kann auf einigen Pentium-Prozessoren ungenau sein|
|[Compilerwarnung (Ebene 1) C4727](../../error-messages/compiler-warnings/compiler-warning-level-1-c4727.md)|PCH namens vorkompilierter Header mit dem gleichen Zeitstempel in Datei1 "und" Datei2 gefunden wurde.  Verwenden zuerst gefundene wird verwendet.|
|Compilerwarnung (Stufe 1) C4728|/ Yl-Option wird ignoriert, da ein PCH-Verweis erforderlich ist.|
|Compilerwarnung (Stufe 4) C4729|Die Funktion ist zu groß für auf Verlaufdiagrammen basierende Warnungen.|
|[Compilerwarnung (Stufe 1) C4730](../../error-messages/compiler-warnings/compiler-warning-level-1-c4730.md)compilerwarnung (Stufe 1) C4730|"main": Kombinieren von _m64 und Gleitkommaausdrücken kann zu fehlerhaftem Code|
|[Compilerwarnung (Ebene 1) C4731](../../error-messages/compiler-warnings/compiler-warning-level-1-c4731.md)|"Zeiger": Framezeigerregister "registrieren" von Inline-Assemblycode geändert|
|Compilerwarnung (Stufe 1) C4732|systeminterne "%s" wird in dieser Architektur nicht unterstützt.|
|[Compilerwarnung (Ebene 1) C4733](../../error-messages/compiler-warnings/compiler-warning-level-1-c4733.md)|Inline-Asm weist "fs": 0: Handler ist nicht als sicherer Handler registriert.|
|[Compilerwarnung (Ebene 3) C4738](../../error-messages/compiler-warnings/compiler-warning-level-3-c4738.md)|Das 32-Bit-Gleitkommaergebnis wird im Speicher gespeichert. Möglicherweise kommt es zu einem Leistungsverlust|
|Compilerwarnung (Stufe 1) C4739|Für den Verweis auf die Variable 'var' ist nicht genügend Speicherplatz vorhanden.|
|[Compilerwarnung (Ebene 4) C4740](../../error-messages/compiler-warnings/compiler-warning-level-4-c4740.md)|Flow für oder gegen Inline-Asm-Code werden globale Optimierung unterdrückt.|
|[Compilerwarnung (Ebene 1) C4742](../../error-messages/compiler-warnings/compiler-warning-level-1-c4742.md)|"Var" hat eine unterschiedliche Ausrichtung in "Datei1" und "Datei2": Anzahl und die Anzahl|
|[Compilerwarnung (Ebene 1) C4743](../../error-messages/compiler-warnings/compiler-warning-level-1-c4743.md)|'Typ' hat eine unterschiedliche Größe in "Datei1" und "Datei2": Anzahl und die Anzahl der Bytes|
|[Compilerwarnung (Ebene 1) C4744](../../error-messages/compiler-warnings/compiler-warning-level-1-c4744.md)|'Var' hat einen anderen Typ in "Datei1" und "Datei2": "Typ1" und "Typ2"|
|[Compilerwarnung C4746](../../error-messages/compiler-warnings/compiler-warning-c4746.md)|flüchtiger Zugriff auf "*Ausdruck*" unterliegt/volatile:\<Iso&#124;ms > festlegen; in Betracht __iso_volatile_load/Store systeminterne Funktionen|
|[Compilerwarnung (Ebene 1) C4747](../../error-messages/compiler-warnings/compiler-warning-level-1-c4747.md)|Aufrufen von verwalteten "Entrypoint": verwalteter Code kann nicht ausgeführt werden, unter der Loadersperre, einschließlich des DLL-Einstiegspunkts und Aufrufen von DLL-Einstiegspunkt eingehen|
|Compilerwarnung (Stufe 4) C4749|bedingt unterstützt: Offsetof auf nicht-standardmäßigen Layouttyp '*Typ*"|
|Compilerwarnung (Stufe 1) C4750|'Bezeichner': Funktion mit „_alloca()“ „inline“ in einer Schleife|
|Compilerwarnung (Stufe 4) C4751|/ arch: AVX gilt nicht für die Intel(R) Streaming SIMD Extensions, die in der Inline-ASM befinden.|
|Compilerwarnung (Stufe 4) C4752|Intel(R) Advanced Vector Extensions; gefunden. Erwägen Sie die Verwendung der/arch: AVX|
|Compilerwarnung (Stufe 4) C4754|Konvertierungsregeln für arithmetische Operationen im Vergleich bei %s(%d) besagen bedeutet, dass ein Branch nicht ausgeführt werden kann. "%S" in "%s" (oder einem ähnlichen Typ mit %d Bytes) umgewandelt.|
|Compilerwarnung C4755|Konvertierungsregeln für arithmetische Operationen im Vergleich bei %s(%d) besagen bedeutet, dass eine Verzweigung in einer Inline-Funktion kann nicht ausgeführt werden. "%S" in "%s" (oder einem ähnlichen Typ mit %d Bytes) umgewandelt.|
|[Compilerwarnung (Ebene 2) C4756](../../error-messages/compiler-warnings/compiler-warning-level-2-c4756.md)|Überlauf bei arithmetischer Auswertung einer Konstanten|
|Compilerwarnung (Stufe 4) C4757|Subskript besteht aus einem großen unsignierten Wert, wollten Sie eine negative Konstante?|
|Compilerwarnung (Stufe 4) C4764|Catch-Objekten, größer als 16 Bytes können nicht ausgerichtet werden.|
|Compilerwarnung (Stufe 4) C4767|Abschnittsname "%s" ist länger als 8 Zeichen und wird vom Linker abgeschnitten|
|Compilerwarnung (Stufe 3) C4768|__declspec-Attribute vor Verknüpfungsspezifikation werden ignoriert.|
|Compilerwarnung C4770|teilweise validierte Enumeration "*Namen*" als Index verwendet|
|Compilerwarnung C4771|Grenzen müssen mit einem einfachen Zeiger erstellt werden. Systeminterne MPX-Funktion ignoriert|
|[Compilerwarnung (Ebene 1, Fehler) C4772](../../error-messages/compiler-warnings/compiler-warning-level-1-c4772.md)|#import auf einen Typ aus einer fehlenden Typbibliothek verwiesen; 'fehlender_Typ"als Platzhalter verwendet|
|Compilerwarnung (Stufe 4) C4774|"*Zeichenfolge*": im Argument erwartet Formatzeichenfolge *Anzahl* ist kein Zeichenfolgenliteral|
|Compilerwarnung (Stufe 3) C4775|in Formatzeichenfolge nicht dem Standard entsprechende Erweiterung '*Zeichenfolge*"von Funktion'*Funktion*"|
|Compilerwarnung (Stufe 1) C4776|"%*Zeichen*"ist nicht zulässig in der Formatzeichenfolge der Funktion"*Funktion*"|
|Compilerwarnung (Stufe 4) C4777|"*Funktion*': Formatzeichenfolge"*Zeichenfolge*"erfordert ein Argument vom Typ"*type1*', Variadic-Argument, aber *Anzahl* weist den Typ "*Typ2*"|
|Compilerwarnung (Stufe 3) C4778|"*Funktion*': nicht abgeschlossene Formatzeichenfolge"*Zeichenfolge*"|
|[Compilerwarnung (Ebene 1) C4788](../../error-messages/compiler-warnings/compiler-warning-level-1-c4788.md)|'Bezeichner': Bezeichner wurde auf 'Anzahl' Zeichen gekürzt|
|[Compilerwarnung (Ebene 1) C4789](../../error-messages/compiler-warnings/compiler-warning-level-1-c4789.md)|Der Puffer 'Bezeichner' mit der Größe von N-Bytes wird überlaufen; M-Bytes werden ab Offset L geschrieben.|
|Compilerwarnung (Stufe 2) C4792|Funktion "%s" deklariert, unter Verwendung von Sysimport und durch Verweis von systemeigenem Code. Importbibliothek ist zum Verknüpfen erforderlich|
|[Compilerwarnung (Ebene 1 und 3) C4793](../../error-messages/compiler-warnings/compiler-warning-level-1-and-3-c4793.md)|'Funktion': Funktion als systemeigene: \n\t'reason kompiliert '|
|Compilerwarnung (Stufe 1) C4794|Segment des lokalen Threadspeicher Variable "%s" von "%s" in "%s" geändert|
|[Compilerwarnung (Ebene 1) C4799](../../error-messages/compiler-warnings/compiler-warning-level-1-c4799.md)|' Funktion ' hat keine EMMS-Anweisung|