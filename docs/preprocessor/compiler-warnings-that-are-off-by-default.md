---
title: Compiler-Warnungen, die standardmäßig deaktiviert sind | Microsoft-Dokumentation
ms.date: 05/30/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- warnings, compiler
- cl.exe compiler, setting options
ms.assetid: 69809cfb-a38a-4035-b154-283a61938df8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b5a4551387716c81766ae99759f8188410497be
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2018
ms.locfileid: "42540429"
---
# <a name="compiler-warnings-that-are-off-by-default"></a>Compiler-Warnungen, die standardmäßig deaktiviert sind
Der Compiler schließt Warnungen, die in der Standardeinstellung deaktiviert werden, da die meisten Entwickler nicht, um sie anzuzeigen möchten. In einigen Fällen stellen eine Auswahl im dar, sie oder allgemeine Idiome in älterem Code sind, oder profitieren Sie von einer Microsoft-Erweiterung für die Sprache. In anderen Fällen geben sie einen Bereich, in denen Programmierer oft falsche Annahmen zu machen die zu unerwarteten oder nicht definierten Verhalten führen können. Einige Warnungen möglicherweise großen abweichungen in der Bibliothek-Header. Die C-Runtime-Bibliotheken und die C++-Standardbibliotheken sollen keine Warnungen nur auf der Warnebene ausgegeben [/W4](../build/reference/compiler-option-warning-level.md).

## <a name="enable-warnings-that-are-off-by-default"></a>Aktivieren von Warnungen, die standardmäßig deaktiviert sind

Sie können Warnungen aktivieren, die normalerweise standardmäßig deaktiviert sind mit einem der folgenden Optionen:

- **#pragma-Warnung (Standardeinstellung:** *Warning_number* **)**

   Die angegebene Warnung (*Warning_number*) auf der Standardebene aktiviert ist. Dokumentation für die Warnung enthält die Standardebene der Warnung.

- **#pragma-Warnung (** *Warning_level* **:** *Warning_number* **)**

   Die angegebene Warnung (*Warning_number*) aktiviert ist, auf der angegebenen Ebene (*Warning_level*).

- [/Wall](../build/reference/compiler-option-warning-level.md)

   `/Wall` aktiviert alle Warnungen, die standardmäßig deaktiviert sind. Wenn Sie diese Option verwenden, Sie können Deaktivieren einzelner Warnungen mithilfe der [/WD](../build/reference/compiler-option-warning-level.md) Option.

- [/ w*Lnnnn*](../build/reference/compiler-option-warning-level.md)

   Dadurch können die Warnung *Nnnn* Ebene *L*.

## <a name="warnings-that-are-off-by-default"></a>Warnungen, die standardmäßig deaktiviert sind

Die folgenden Warnungen sind in Visual Studio 2015 und höher standardmäßig deaktiviert:

|||
|-|-|
|[C4061](../error-messages/compiler-warnings/compiler-warning-level-4-c4061.md) (Ebene 4)|Enumerator '*Bezeichner*"in einem Schalter der Enumeration'*Enumeration*" wird nicht von einer Case-Bezeichnung explizit behandelt|
|[C4062](../error-messages/compiler-warnings/compiler-warning-level-4-c4062.md) (Ebene 4)|Enumerator '*Bezeichner*"in einem Schalter der Enumeration'*Enumeration*" wird nicht verarbeitet|
|C4191 (Ebene 3)|"*Operator*": unsichere Konvertierung von '*Type_of_expression*'to'*Type_required*"|
|[C4242](../error-messages/compiler-warnings/compiler-warning-level-4-c4242.md) (Ebene 4)|"*Bezeichner*': Konvertierung von '*type1*'to'*Typ2*", möglicher Datenverlust|
|[C4254](../error-messages/compiler-warnings/compiler-warning-level-4-c4254.md) (Ebene 4)|"*Operator*': Konvertierung von '*type1*'to'*Typ2*", möglicher Datenverlust|
|[C4255](../error-messages/compiler-warnings/compiler-warning-level-4-c4255.md) (Ebene 4)|"*Funktion*': Kein Funktionsprototyp angegeben: '()" zu "(void)" konvertiert|
|[C4263](../error-messages/compiler-warnings/compiler-warning-level-4-c4263.md) (Ebene 4)|"*Funktion*': Memberfunktion überschreibt keine virtuelle Memberfunktion einer Basisklasse nicht|
|[C4264](../error-messages/compiler-warnings/compiler-warning-level-1-c4264.md) (Ebene 1)|"*Virtual_function*": keine Überschreibung für virtuelle Memberfunktion der Basis verfügbar "*Klasse*"; die Funktion wird ausgeblendet|
|[C4265](../error-messages/compiler-warnings/compiler-warning-level-3-c4265.md) (Ebene 3)|"*Klasse*": Klasse besitzt virtuelle Funktionen, aber der Destruktor ist nicht virtuell|
|[C4266](../error-messages/compiler-warnings/compiler-warning-level-4-c4266.md) (Ebene 4)|"*Funktion*": keine Überschreibung für virtuelle Memberfunktion der Basis verfügbar "*Typ*"; die Funktion wird ausgeblendet|
|[C4287](../error-messages/compiler-warnings/compiler-warning-level-3-c4287.md) (Ebene 3)|"*Operator*": unsigned/Negative-konstantenkonflikt|
|[C4289](../error-messages/compiler-warnings/compiler-warning-level-4-c4289.md) (Ebene 4)|nicht dem Standard entsprechende Erweiterung: "*Var*': Loop-Steuerelementvariable, die in der for-Schleife deklariert wurde, wird außerhalb der for-Schleife-Bereich|
|[C4296](../error-messages/compiler-warnings/compiler-warning-level-4-c4296.md) (Ebene 4)|"*Operator*': Ausdruck ist immer" false "|
|[C4339](../error-messages/compiler-warnings/compiler-warning-level-4-c4339.md) (Ebene 4)|"*Typ*": Verwendung eines undefinierten Typs wurde entdeckt. im CLR - Metadaten verwenden dieses Typs führt möglicherweise zu einer Laufzeitausnahme|
|[C4342](../error-messages/compiler-warnings/compiler-warning-level-1-c4342.md) (Ebene 1)|verhaltensänderung: '*Funktion*"aufgerufen wird, jedoch ein Memberoperator aufgerufen wurde, in früheren Versionen|
|[C4350](../error-messages/compiler-warnings/compiler-warning-level-1-c4350.md) (Ebene 1)|verhaltensänderung: '*member1*"anstelle des Namens"*member2*"|
|[C4355](../error-messages/compiler-warnings/compiler-warning-c4355.md)|"this": Wird in der Basisliste für den Memberinitialisierer verwendet|
|[C4365](../error-messages/compiler-warnings/compiler-warning-level-4-c4365.md) (Ebene 4)|"*Aktion*': Konvertierung von '*TYP_1*'to'*TYP_2*", signed/unsigned-Konflikt|
|C4370 (Ebene 3)|Durch bessere Verpackung wurde das Klassenlayout geändert, das vorher eine andere Compilerversion hatte|
|[C4371](../error-messages/compiler-warnings/c4371.md) (Ebene 3)|"*Classname*': Layout der Klasse möglicherweise von einer früheren Version des Compilers durch bessere Verpackung des Members geändert"*Member*"|
|C4388 (Ebene 4)|Konflikt zwischen 'signed' und 'unsigned'|
|[C4412](../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md) (Ebene 2)|"*Funktion*': Funktionssignatur enthält Typ '*Typ*'; C++-Objekte sind nicht sicher zwischen reinem Code übergeben und gemischtem bzw. systemeigenem|
|C4426 (Ebene 1)|die optimierungskennzeichnungen wurden geändert, nachdem das Einschließen des Headers, möglicherweise aufgrund von #pragma optimize() <sup>14.1</sup>|
|[C4435](../error-messages/compiler-warnings/compiler-warning-level-4-c4435.md) (Ebene 4)|"*class1*': das Objektlayout unter" / vd2 "ändert sich aufgrund der virtuellen Basis '*Klasse2*"|
|[C4437](../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md) (Ebene 4)|Dynamic_cast von virtueller Basis '*class1*'to'*Klasse2*' kann in einigen Kontexten fehl|
|C4444 (Ebene 3)|Höchste Ebene '__unaligned' ist in diesem Kontext nicht implementiert|
|[C4464](../error-messages/compiler-warnings/c4464.md) (Ebene 4)|Relative Includepfad enthält '..'|
|[C4471](../error-messages/compiler-warnings/compiler-warning-level-4-c4471.md) (Ebene 4)|eine Vorwärtsdeklaration einer Enumeration ohne bereichseinschränkung müssen einen zugrunde liegenden Typ (Int wird angenommen) <sup>permanent festlegen</sup>|
|C4472 (Ebene 1)|"*Bezeichner*" ist eine systemeigene Enumeration: Fügen Sie einen Zugriffsspezifizierer (privat/öffentlich), um eine verwaltete Enumeration zu deklarieren.|
|[C4514](../error-messages/compiler-warnings/compiler-warning-level-4-c4514.md) (Ebene 4)|"*Funktion*': nicht referenzierte Inlinefunktion wurde entfernt|
|[C4536](../error-messages/compiler-warnings/compiler-warning-level-4-c4536.md) (Ebene 4)|'Type Name': Typ größer als das Metadatenlimit von "*Grenzwert*' Zeichen|
|[C4545](../error-messages/compiler-warnings/compiler-warning-level-1-c4545.md) (Ebene 1)|Ausdruck vor dem Komma wird als Funktion ausgewertet, der eine Argumentliste fehlt|
|[C4546](../error-messages/compiler-warnings/compiler-warning-level-1-c4546.md) (Ebene 1)|Funktionsaufruf vor dem Komma ohne Argumentliste|
|[C4547](../error-messages/compiler-warnings/compiler-warning-level-1-c4547.md) (Ebene 1)|"*Operator*': Operator vor dem Komma keine Auswirkungen hat; Operator mit Nebeneffekten erwartet|
|[C4548](../error-messages/compiler-warnings/compiler-warning-level-1-c4548.md) (Ebene 1)|Ausdruck vor dem Komma hat keine Auswirkung; es wurde ein Ausdruck mit Nebeneffekt erwartet|
|[C4549](../error-messages/compiler-warnings/compiler-warning-level-1-c4549.md) (Ebene 1)|"*operator1*': Operator vor dem Komma hat keine Auswirkungen; wollten Sie"*operator2*"?|
|[C4555](../error-messages/compiler-warnings/compiler-warning-level-1-c4555.md) (Ebene 1)|Der Ausdruck hat keine Auswirkungen; Ausdruck mit Nebeneffekten erwartet|
|[C4557](../error-messages/compiler-warnings/compiler-warning-level-3-c4557.md) (Ebene 3)|"__assume" enthält den Effekt '*Auswirkung*"|
|[C4571](../error-messages/compiler-warnings/compiler-warning-level-4-c4571.md) (Ebene 4)|Information: catch(...)-Semantik Visual C++ 7.1 geändert; strukturierte Ausnahmen (SEH) werden nicht mehr abgefangen.|
|C4574 (Ebene 4)|"*Bezeichner*"ist gemäß Definition "0": wollten Sie verwenden "#if *Bezeichner*"?|
|C4577 (Ebene 1)|"Noexcept" mit ohne angegebenen ausnahmebehandlungsmodus verwendet; Beendigung bei einer Ausnahme ist nicht garantiert. Geben Sie/EHsc|
|C4582 (Ebene 4)|"*Typ*": Konstruktor wird nicht implizit aufgerufen.|
|C4583 (Ebene 4)|"*Typ*": Destruktor wird nicht implizit aufgerufen.|
|C4587 (Ebene 1)|"*Anonymous_structure*": verhaltensänderung: Konstruktor wird nicht mehr implizit aufgerufen.|
|C4588 (Ebene 1)|"*Anonymous_structure*": verhaltensänderung: Destruktor wird nicht mehr implizit aufgerufen.|
|C4596 (Ebene 4)|"*Bezeichner*": Unzulässiger vollständig angegebener Name in Elementdeklaration <sup>14.3</sup> <sup>permanent festlegen</sup>|
|C4598 (Ebene 1 und Ebene 3)|' #include "*Header*" ": Anzahl der Header *Anzahl* in der vorkompilierten Headerdatei entspricht nicht aktuellen Kompilierung an dieser Position <sup>14.3</sup>|
|C4599 (Ebene 3)|"*Option* *Pfad*': Befehlszeilenargument Anzahl *Anzahl* entspricht vorkompilierte Header nicht <sup>14.3</sup>|
|C4605 (Ebene 1)|' / D*Makro*"in der aktuellen Befehlszeile angegeben, jedoch wurde nicht angegeben, wenn die vorkompilierter Header erstellt wurde|
|[C4608](../error-messages/compiler-warnings/compiler-warning-level-3-c4608.md) (Ebene 3)|"*Union_member*"wurde bereits initialisiert von einem anderen union-Member in der Initialisiererliste"*Union_member*" <sup>permanent festlegen</sup>|
|[C4619](../error-messages/compiler-warnings/compiler-warning-level-3-c4619.md) (Ebene 3)|#pragma-Warnung: Es gibt keine Warnungsnummer '*Anzahl*"|
|[C4623](../error-messages/compiler-warnings/compiler-warning-level-4-c4623.md) (Ebene 4)|'Abgeleitete Klasse': Der Standardkonstruktor konnte nicht generiert werden, da auf einen Basisklassen-Standardkonstruktor nicht zugegriffen werden kann|
|[C4625](../error-messages/compiler-warnings/compiler-warning-level-4-c4625.md) (Ebene 4)|'Abgeleitete Klasse': Der Kopierkonstruktor konnte nicht generiert werden, da auf einen Basisklassen-Kopierkonstruktor nicht zugegriffen werden kann|
|[C4626](../error-messages/compiler-warnings/compiler-warning-level-4-c4626.md) (Ebene 4)|'Abgeleitete Klasse': Der Zuweisungsoperator konnte nicht generiert werden, da auf einen Basisklassen-Zuweisungsoperator nicht zugegriffen werden kann|
|[C4628](../error-messages/compiler-warnings/compiler-warning-level-1-c4628.md) (Ebene 1)|'digraphs' werden mit '-Ze' nicht unterstützt. Zeichenfolge '*Digraph*"nicht als alternatives Token für interpretiert"*Char*"|
|[C4640](../error-messages/compiler-warnings/compiler-warning-level-3-c4640.md) (Ebene 3)|"*Instanz*": Erstellen eines lokalen static-Objekts ist nicht threadsicher|
|C4647 (Ebene 3)|Verändertes Programmverhalten: __is_pod (*Typ*) verfügt über unterschiedliche Wert in früheren Versionen|
|C4654 (Ebene 4)|Einschließen von Code, die vor platziert der vorkompilierten Headerdatei wird, wird ignoriert. Fügen Sie dem vorkompilierten Header Code hinzu. <sup>14.1</sup>|
|[C4668](../error-messages/compiler-warnings/compiler-warning-level-4-c4668.md) (Ebene 4)|"*Symbol*"ist nicht definiert als ein Präprozessormakro, und Ersetzen Sie dabei mit "0" für"*Direktiven*"|
|[C4682](../error-messages/compiler-warnings/compiler-warning-level-4-c4682.md) (Ebene 4)|"*Symbol*': kein direktionales Parameterattribut angegeben, Standardwert [in]|
|[C4686](../error-messages/compiler-warnings/compiler-warning-level-3-c4686.md) (Ebene 3)|"*einen benutzerdefinierten Typ*": mögliche verhaltensänderung, Änderung in der UDT gibt zurück Aufrufkonvention|
|[C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) (Ebene 1)|"*Funktion*': die Signatur des nicht privaten Members enthält den privaten systemeigenen Assemblytyp '*Native_type*"|
|[C4710](../error-messages/compiler-warnings/compiler-warning-level-4-c4710.md) (Ebene 4)|"*Funktion*': Funktion, die nicht" inline "|
|[C4738](../error-messages/compiler-warnings/compiler-warning-level-3-c4738.md) (Ebene 3)|Das 32-Bit-Gleitkommaergebnis wird im Speicher gespeichert. Möglicherweise kommt es zu einem Leistungsverlust|
|[C4746](../error-messages/compiler-warnings/compiler-warning-c4746.md)|flüchtiger Zugriff auf "*Ausdruck*" unterliegt/volatile:\<Iso&#124;ms > festlegen; in Betracht __iso_volatile_load/Store systeminterne Funktionen|
|C4749 (Ebene 4)|bedingt unterstützt: Offsetof auf nicht-standardmäßigen Layouttyp '*Typ*"|
|C4767 (Ebene 4)|Name des Abschnitts "*Symbol*' ist länger als 8 Zeichen und wird vom Linker abgeschnitten|
|C4768 (Ebene 3)|__declspec-Attribute vor Verknüpfungsspezifikation werden ignoriert.|
|C4774 (Ebene 4)|"*Zeichenfolge*": im Argument erwartet Formatzeichenfolge *Anzahl* ist kein Zeichenfolgenliteral|
|C4777 (Ebene 4)|"*Funktion*': Formatzeichenfolge"*Zeichenfolge*"erfordert ein Argument vom Typ"*type1*', Variadic-Argument, aber *Anzahl* weist den Typ "*Typ2*"|
|C4786 (Ebene 3)|"*Symbol*': Objektname wurde gekürzt, um"*Anzahl*"Zeichen in den Informationen zum Debuggen|
|[C4820](../error-messages/compiler-warnings/compiler-warning-level-4-c4820.md) (Ebene 4)|"*Bytes*'Bytes Abstand hinzugefügten nach dem Konstrukt'*Member_name*"|
|C4826 (Ebene 2)|Konvertierung von '*type1*'to'*Typ2*' ist signaturerweitert. Dies kann zu unerwartetem Laufzeitverhalten führen.|
|C4837 (Ebene 4)|Trigraph gefunden: "?? *Zeichen*"ersetzt durch"*Zeichen*"|
|C4841 (Ebene 4)|nicht standardmäßige Erweiterung verwendet: zusammengesetzter memberkennzeichner in Offsetof verwendeter Bezeichner|
|C4842 (Ebene 4)|Das Ergebnis von 'Offsetof' wird auf einen Typ mit mehrfacher Vererbung ist nicht garantiert konsistent Compiler-Versionen|
|[C4868](../error-messages/compiler-warnings/compiler-warning-c4868.md) (Ebene 4)|"_Datei_(*Line_number*)" erzwingen Compiler möglicherweise nicht die Reihenfolge der Auswertung von links nach rechts in der Initialisierungsliste|
|[C4905](../error-messages/compiler-warnings/compiler-warning-level-1-c4905.md) (Ebene 1)|Breites Zeichenfolgenliteral umgewandelt zu "LPSTR"|
|[C4906](../error-messages/compiler-warnings/compiler-warning-level-1-c4906.md) (Ebene 1)|Zeichenfolgenliteral umgewandelt zu "LPWSTR"|
|[C4917](../error-messages/compiler-warnings/compiler-warning-level-1-c4917.md) (Ebene 1)|"*Deklarator*': eine GUID kann nur eine Klasse, Schnittstelle oder Namespace zugeordnet werden|
|[C4928](../error-messages/compiler-warnings/compiler-warning-level-1-c4928.md) (Ebene 1)|Unzulässige Kopierinitialisierung. Mehrere benutzerdefinierte Konvertierungen wurden implizit übernommen|
|[C4931](../error-messages/compiler-warnings/compiler-warning-level-4-c4931.md) (Ebene 4)|Es wird angenommen, dass die Typbibliothek für Anzahl-Bit-Pointer erstellt wurde|
|[C4946](../error-messages/compiler-warnings/compiler-warning-level-1-c4946.md) (Ebene 1)|Reinterpret_cast wird zwischen verknüpften Klassen verwendet: "*class1*'und'*Klasse2*"|
|C4962|"*Funktion*': Profilgesteuerte Optimierungen wurden deaktiviert, da die Optimierungen eine Inkonsistenz zwischen den Profildaten verursacht wurde.|
|[C4986](../error-messages/compiler-warnings/compiler-warning-c4986.md) (Ebene 4)|"*Symbol*': Ausnahmespezifikation stimmt nicht mit der vorherigen Deklaration überein|
|C4987 (Ebene 4)|Es wurde eine nicht standardmäßige Erweiterung verwendet: 'throw (...)'|
|C4988 (Ebene 4)|"*Symbol*': Variable, die außerhalb von Klassen-/Funktionsbereichs deklariert|
|C5022|"*Typ*": mehrere bewegungskonstruktoren angegeben|
|C5023|"*Typ*": mehrere bewegungszuweisungsoperatoren angegeben|
|C5024 (Ebene 4)|"*Typ*": Konstruktor wurde implizit als gelöscht definiert.|
|C5025 (Ebene 4)|"*Typ*': Verschieben der Zuweisungsoperator wurde implizit als gelöscht definiert.|
|C5026 (Ebene 1 und Stufe 4)|"*Typ*": Konstruktor wurde implizit als gelöscht definiert.|
|C5027 (Ebene 1 und Stufe 4)|"*Typ*': Verschieben der Zuweisungsoperator wurde implizit als gelöscht definiert.|
|C5029 (Ebene 4)|nicht dem Standard entsprechende Erweiterung: Ausrichtungsattribute in C++, die auf Variablen, Datenmember und Tagtypen nur anwenden|
|C5031 (Ebene 4)|#pragma warning"(POP): wahrscheinlich fehlzuordnung, POP-Warnstatus in anderen Datei mithilfe von Push übertragen <sup>14.1</sup>|
|C5032 (Ebene 4)|#pragma warning"(Push) ohne entsprechende #pragma warning"(POP) erkannt <sup>14.1</sup>|
|C5034|Verwenden der systeminternen "*systeminterne*' bewirkt, dass Funktion *Funktion* als gastcode kompiliert <sup>15.3</sup>|
|C5035|Verwenden des Features "*Feature*' bewirkt, dass Funktion *Funktion* als gastcode kompiliert <sup>15.3</sup>|
|C5036 (Ebene 1)|VarArgs-Funktion zeigerkonvertierung beim Kompilieren mit/Hybrid: x86arm64 "*type1*'to'*Typ2*" <sup>15.3</sup>|
|[C5038](../error-messages/compiler-warnings/c5038.md) (Ebene 4)|Datenmember "*member1*"wird nach Datenmember initialisiert werden"*member2*" <sup>15.3</sup>|
|C5039 (Ebene 4)|"*Funktion*': Zeiger oder Verweis auf die möglicherweise auslösende Funktion übergeben" extern "C-Funktion unter - EHc übergeben. Nicht definiertes Verhalten kann auftreten, wenn diese Funktion eine Ausnahme auslöst. <sup>Version 15.5</sup>|
|C5042 (Ebene 3)|"*Funktion*": Funktionsdeklarationen im Blockbereich können nicht "Inline" angegeben werden, in Standard-c++, entfernen Sie 'Inline'-Spezifizierer <sup>15.5</sup>|
|[C5045](../error-messages/compiler-warnings/c5045.md)|Compiler fügt die Spectre-Entschärfung für die Auslastung des Arbeitsspeichers, wenn "/ qspectre" Schalter angegeben <sup>15.7</sup>|

<sup>14.1</sup> diese Warnung ist verfügbar in Visual Studio 2015 Update 1.  
<sup>14.3</sup> diese Warnung ist verfügbar in Visual Studio 2015 Update 3.  
<sup>15.3</sup> diese Warnung ist verfügbar in Visual Studio 2017 Version 15.3.  
<sup>15.5</sup> diese Warnung ist verfügbar in Visual Studio 2017 Version 15.5.  
<sup>15.7</sup> diese Warnung wird in Visual Studio 2017 Version 15.7 ab.  
<sup>Perm</sup> diese Warnung ist deaktiviert, es sei denn, die [/ PERMISSIVE--](../build/reference/permissive-standards-conformance.md) Compiler-Option festgelegt ist.  

## <a name="warnings-off-by-default-in-earlier-versions"></a>Warnungen deaktivieren, wird standardmäßig in früheren Versionen

Diese Warnungen wurden deaktiviert standardmäßig in der Compiler vor Visual Studio 2015-Versionen:

|||
|-|-|
|[C4302](../error-messages/compiler-warnings/compiler-warning-level-2-c4302.md) (Ebene 2)|"*Konvertierung*': Verkürzung von '*type1*'to'*Typ2*"|
|[C4311](../error-messages/compiler-warnings/compiler-warning-level-1-c4311.md) (Ebene 1)|"*Variable*': zeigerverkürzung von '*Typ*'to'*Typ*"|
|[C4312](../error-messages/compiler-warnings/compiler-warning-level-1-c4312.md) (Ebene 1)|"*Vorgang*': Konvertierung von '*type1*'to'*Typ2*" größeren|
|[C4319](../error-messages/compiler-warnings/compiler-warning-level-1-c4319.md) (Ebene 1)|"*Operator*": Null erweitert "*type1*'to'*Typ2*" größeren|

Diese Warnung wurde deaktiviert, wird standardmäßig in Versionen des Compilers vor Visual Studio 2012:

|||
|-|-|
|[C4431](../error-messages/compiler-warnings/compiler-warning-level-4-c4431.md) (Ebene 4)|Fehlender Typspezifizierer - int wird angenommen. Hinweis: default-int wird von C++ nicht unterstützt|

## <a name="see-also"></a>Siehe auch

[warning](../preprocessor/warning.md)