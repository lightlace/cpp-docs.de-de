---
title: Compiler-Warnungen, die standardmäßig deaktiviert sind | Microsoft Docs
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
ms.openlocfilehash: d311c730781aee70d4b77723ddec98a79407e42a
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705565"
---
# <a name="compiler-warnings-that-are-off-by-default"></a>Compiler-Warnungen standardmäßig deaktiviert sind

Der Compiler schließt Warnungen ein, die standardmäßig deaktiviert, da die meisten Entwickler nicht, um sie anzuzeigen möchten. In einigen Fällen eine stilistischer Wahl darstellen oder sind allgemeine Idiome in älterem Code oder eine Microsoft-Erweiterung zur Programmiersprache nutzen. In anderen Fällen geben sie einen Bereich, in denen Programmierer häufig falsche Annahmen stellen, die zu unerwarteten oder nicht definierten Verhalten führen kann. Einige Warnungen möglicherweise großen abweichungen in der Bibliothek-Header. Der C-Laufzeitbibliotheken und die C++-Standardbibliotheken dienen zum Ausgeben von keine Warnungen nur auf der Warnebene [/W4](../build/reference/compiler-option-warning-level.md).

## <a name="enable-warnings-that-are-off-by-default"></a>Aktivieren von Warnungen, die standardmäßig deaktiviert sind

Sie können Warnungen aktivieren, die normalerweise standardmäßig sind deaktiviert mithilfe einer der folgenden Optionen:

- **#pragma Warning (Standard:** *Warning_number* **)**

   Die angegebene Warnung (*Warning_number*) auf der Standardebene aktiviert ist. Dokumentation für die Warnung enthält die Standardebene der Warnung.

- **#pragma Warning (** *Warning_level* **:** *Warning_number* **)**

   Die angegebene Warnung (*Warning_number*) aktiviert ist, auf der angegebenen Ebene (*Warning_level*).

- [/Wall](../build/reference/compiler-option-warning-level.md)

   **/ Wall** aktiviert alle Warnungen, die standardmäßig deaktiviert sind. Wenn Sie diese Option verwenden, Sie können einzelne Warnungen über Deaktivieren der [/WD](../build/reference/compiler-option-warning-level.md) Option.

- [/ w*Lnnnn*](../build/reference/compiler-option-warning-level.md)

   Dadurch können die Warnung *Nnnn* Ebene *L*.

## <a name="warnings-that-are-off-by-default"></a>Warnungen, die standardmäßig deaktiviert sind

Die folgenden Warnungen werden in Visual Studio 2015 und höher standardmäßig deaktiviert:

|||
|-|-|
|[C4061](../error-messages/compiler-warnings/compiler-warning-level-4-c4061.md) (Stufe 4)|Enumerator '*Bezeichner*'in Switch Enum'*Enumeration*"wird nicht von einer Case-Bezeichnung explizit behandelt|
|[C4062](../error-messages/compiler-warnings/compiler-warning-level-4-c4062.md) (Stufe 4)|Enumerator '*Bezeichner*'in Switch Enum'*Enumeration*"wird nicht verarbeitet|
|C4191 (Ebene 3)|"*Operator*': unsichere Konvertierung von '*Type_of_expression*'to'*Type_required*"|
|[C4242](../error-messages/compiler-warnings/compiler-warning-level-4-c4242.md) (Stufe 4)|"*Bezeichner*': Konvertierung von '*Typ1*'to'*Typ2*', möglicher Datenverlust|
|[C4254](../error-messages/compiler-warnings/compiler-warning-level-4-c4254.md) (Stufe 4)|"*Operator*': Konvertierung von '*Typ1*'to'*Typ2*', möglicher Datenverlust|
|[C4255](../error-messages/compiler-warnings/compiler-warning-level-4-c4255.md) (Stufe 4)|"*Funktion*': Kein Funktionsprototyp angegeben: '()', '(void)' konvertieren|
|[C4263](../error-messages/compiler-warnings/compiler-warning-level-4-c4263.md) (Stufe 4)|"*Funktion*': Memberfunktion überschreibt keine virtuelle Memberfunktion Basisklasse nicht|
|[C4264](../error-messages/compiler-warnings/compiler-warning-level-1-c4264.md) (Stufe 1)|"*Virtual_function*': keine Überschreibung für virtuelle Memberfunktion der Basis verfügbar"*Klasse*"; die Funktion wird ausgeblendet|
|[C4265](../error-messages/compiler-warnings/compiler-warning-level-3-c4265.md) (Stufe 3)|"*Klasse*': Klasse verfügt über virtuelle Funktionen, aber der Destruktor ist nicht virtuell|
|[C4266](../error-messages/compiler-warnings/compiler-warning-level-4-c4266.md) (Stufe 4)|"*Funktion*': keine Überschreibung für virtuelle Memberfunktion der Basis verfügbar"*Typ*"; die Funktion wird ausgeblendet|
|[C4287](../error-messages/compiler-warnings/compiler-warning-level-3-c4287.md) (Stufe 3)|"*Operator*": vorzeichenloser und negativer Konstante Konflikt|
|[C4289](../error-messages/compiler-warnings/compiler-warning-level-4-c4289.md) (Stufe 4)|nicht dem Standard entsprechende Erweiterung: '*Var*": Loop-Steuerelementvariable, die in der for-Schleife deklariert wird, außerhalb des for-Schleife|
|[C4296](../error-messages/compiler-warnings/compiler-warning-level-4-c4296.md) (Stufe 4)|"*Operator*": Ausdruck ist immer "false"|
|[C4339](../error-messages/compiler-warnings/compiler-warning-level-4-c4339.md) (Stufe 4)|"*Typ*': Verwendung eines undefinierten Typs erkannt werden in CLR - Metadaten verwenden dieses Typs führt möglicherweise zu einer Laufzeitausnahme|
|[C4342](../error-messages/compiler-warnings/compiler-warning-level-1-c4342.md) (Stufe 1)|verhaltensänderung: '*Funktion*"aufgerufen wird, jedoch ein Memberoperator aufgerufen wurde, in früheren Versionen|
|[C4350](../error-messages/compiler-warnings/compiler-warning-level-1-c4350.md) (Stufe 1)|verhaltensänderung: '*member1*"anstelle des Namens"*member2*"|
|[C4355](../error-messages/compiler-warnings/compiler-warning-c4355.md)|"this": Wird in der Basisliste für den Memberinitialisierer verwendet|
|[C4365](../error-messages/compiler-warnings/compiler-warning-level-4-c4365.md) (Stufe 4)|"*Aktion*': Konvertierung von '*TYP_1*'to'*TYP_2*', Konflikt mit/ohne Vorzeichen|
|C4370 (Stufe 3)|Durch bessere Verpackung wurde das Klassenlayout geändert, das vorher eine andere Compilerversion hatte|
|[C4371](../error-messages/compiler-warnings/c4371.md) (Stufe 3)|"*Classname*": möglicherweise von einer früheren Version des Compilers aufgrund bessere Verpackung des Members Klassenlayout geändert "*Member*"|
|C4388 (Stufe 4)|Konflikt zwischen 'signed' und 'unsigned'|
|[C4412](../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md) (Ebene 2)|"*Funktion*': Funktionssignatur enthält Typ '*Typ*'; C++-Objekte sind nicht sicher zwischen reinem Code übergeben und gemischtem oder systemeigenem|
|C4426 (Stufe 1)|optimierungseinstellungen geändert, nachdem einschließlich Header, möglicherweise aufgrund von #pragma optimize() <sup>14,1</sup>|
|[C4435](../error-messages/compiler-warnings/compiler-warning-level-4-c4435.md) (Stufe 4)|"*class1*': das Objektlayout unter/vd2 ändert sich aufgrund der virtuellen Basis '*Klasse2*"|
|[C4437](../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md) (Stufe 4)|Dynamic_cast von virtueller Basis '*class1*'to'*Klasse2*' konnte in einigen Kontexten fehl|
|C4444 (Stufe 3)|Höchste Ebene '__unaligned' ist in diesem Kontext nicht implementiert|
|[C4464](../error-messages/compiler-warnings/c4464.md) (Stufe 4)|Relative Includepfad enthält '..'|
|[C4471](../error-messages/compiler-warnings/compiler-warning-level-4-c4471.md) (Stufe 4)|eine Vorwärtsdeklaration einer Enumeration ohne bereichseinschränkung benötigen einen zugrunde liegenden Typ (Int wird angenommen) <sup>permanent</sup>|
|C4472 (Stufe 1)|"*Bezeichner*" ist eine systemeigene Enumeration: Fügen Sie einen Zugriffsspezifizierer (privat/öffentlich), um eine verwaltete Enumeration zu deklarieren.|
|[C4514](../error-messages/compiler-warnings/compiler-warning-level-4-c4514.md) (Stufe 4)|"*Funktion*': nicht referenzierte Inlinefunktion wurde entfernt|
|[C4536](../error-messages/compiler-warnings/compiler-warning-level-4-c4536.md) (Stufe 4)|"Typname": Typ größer als das Metadatenlimit von '*Grenzwert*' Zeichen|
|[C4545](../error-messages/compiler-warnings/compiler-warning-level-1-c4545.md) (Stufe 1)|Ausdruck vor dem Komma wird als Funktion ausgewertet, der eine Argumentliste fehlt|
|[C4546](../error-messages/compiler-warnings/compiler-warning-level-1-c4546.md) (Stufe 1)|Funktionsaufruf vor dem Komma ohne Argumentliste|
|[C4547](../error-messages/compiler-warnings/compiler-warning-level-1-c4547.md) (Stufe 1)|"*Operator*': Operator vor dem Komma keine Auswirkungen hat; Operator mit Nebeneffekten erwartet|
|[C4548](../error-messages/compiler-warnings/compiler-warning-level-1-c4548.md) (Stufe 1)|Ausdruck vor dem Komma hat keine Auswirkung; es wurde ein Ausdruck mit Nebeneffekt erwartet|
|[C4549](../error-messages/compiler-warnings/compiler-warning-level-1-c4549.md) (Stufe 1)|"*operator1*': Operator vor dem Komma hat keine Auswirkungen; wollten Sie"*operator2*"?|
|[C4555](../error-messages/compiler-warnings/compiler-warning-level-1-c4555.md) (Stufe 1)|Der Ausdruck hat keine Auswirkungen; Ausdruck mit Nebeneffekten erwartet|
|[C4557](../error-messages/compiler-warnings/compiler-warning-level-3-c4557.md) (Stufe 3)|"__assume' enthält den Effekt '*Effekt*"|
|[C4571](../error-messages/compiler-warnings/compiler-warning-level-4-c4571.md) (Stufe 4)|Information: catch(...)-Semantik seit Visual C++ 7.1 geändert; strukturierte Ausnahmen (SEH) werden nicht mehr abgefangen.|
|C4574 (Stufe 4)|"*Bezeichner*'definiert ' 0': wollten Sie verwenden" #if *Bezeichner*"?|
|C4577 (Stufe 1)|"Noexcept" verwendet, mit der keine Ausnahmebehandlung angegebenen Modus; Beenden von Ausnahme ist nicht gewährleistet. Geben Sie/EHsc|
|C4582 (Stufe 4)|"*Typ*': Konstruktor wird nicht implizit aufgerufen.|
|C4583 (Stufe 4)|"*Typ*": Destruktor wird nicht implizit aufgerufen.|
|C4587 (Stufe 1)|"*Anonymous_structure*": verhaltensänderung: Konstruktor wird nicht mehr implizit aufgerufen.|
|C4588 (Stufe 1)|"*Anonymous_structure*": verhaltensänderung: Destruktor wird nicht mehr implizit aufgerufen.|
|C4596 (Stufe 4)|"*Bezeichner*': Unzulässiger gekennzeichneter Name in Memberdeklaration <sup>14.3</sup> <sup>permanent</sup>|
|C4598 (Ebene 1 und Stufe 3)|' #include "*Header*" ": Anzahl der Header *Anzahl* im des vorkompilierten Headers stimmt nicht mit aktuellen Kompilierung an dieser Position <sup>14.3</sup>|
|C4599 (Stufe 3)|"*Option* *Pfad*": Befehlszeilenargument Anzahl *Anzahl* entspricht vorkompilierte Header nicht <sup>14.3</sup>|
|C4605 (Stufe 1)|"/ D*Makro*" auf der aktuellen Befehlszeile durchführen angegeben, aber wurde nicht angegeben, wenn der vorkompilierter Header erstellt wurde|
|[C4608](../error-messages/compiler-warnings/compiler-warning-level-3-c4608.md) (Stufe 3)|"*Union_member*"bereits initialisiert wurde von einem anderen union-Member in der Initialisiererliste"*Union_member*" <sup>permanent</sup>|
|[C4619](../error-messages/compiler-warnings/compiler-warning-level-3-c4619.md) (Stufe 3)|#pragma-Warnung: Es ist keine Warnungsnummer '*Anzahl*"|
|[C4623](../error-messages/compiler-warnings/compiler-warning-level-4-c4623.md) (Stufe 4)|'Abgeleitete Klasse': Der Standardkonstruktor konnte nicht generiert werden, da auf einen Basisklassen-Standardkonstruktor nicht zugegriffen werden kann|
|[C4625](../error-messages/compiler-warnings/compiler-warning-level-4-c4625.md) (Stufe 4)|'Abgeleitete Klasse': Der Kopierkonstruktor konnte nicht generiert werden, da auf einen Basisklassen-Kopierkonstruktor nicht zugegriffen werden kann|
|[C4626](../error-messages/compiler-warnings/compiler-warning-level-4-c4626.md) (Stufe 4)|'Abgeleitete Klasse': Der Zuweisungsoperator konnte nicht generiert werden, da auf einen Basisklassen-Zuweisungsoperator nicht zugegriffen werden kann|
|[C4628](../error-messages/compiler-warnings/compiler-warning-level-1-c4628.md) (Stufe 1)|'digraphs' werden mit '-Ze' nicht unterstützt. Zeichenfolge "*Digraph*"nicht als alternativer Token für interpretiert"*Char*"|
|[C4640](../error-messages/compiler-warnings/compiler-warning-level-3-c4640.md) (Stufe 3)|"*Instanz*": Erstellen eines lokalen static-Objekts ist nicht threadsicher|
|C4647 (Stufe 3)|Verändertes Programmverhalten: __is_pod (*Typ*) anderen Wert aufweist, in früheren Versionen|
|C4654 (Stufe 4)|Code platziert werden, bevor der vorkompilierten Headerdatei umfassen Zeile werden ignoriert. Fügen Sie Code, um vorkompilierte Header. <sup>14,1</sup>|
|[C4668](../error-messages/compiler-warnings/compiler-warning-level-4-c4668.md) (Stufe 4)|"*Symbol*'ist nicht definiert als ein Präprozessormakro, ersetzen durch '0' für'*Direktiven*"|
|[C4682](../error-messages/compiler-warnings/compiler-warning-level-4-c4682.md) (Stufe 4)|"*Symbol*': kein direktionales Parameterattribut angegeben, Standardwert [in]|
|[C4686](../error-messages/compiler-warnings/compiler-warning-level-3-c4686.md) (Stufe 3)|"*einen benutzerdefinierten Typ*': mögliche Änderung im Verhalten in der UDT gibt Aufrufkonvention zurück|
|[C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) (Stufe 1)|"*Funktion*": die Signatur des nicht privaten Members enthält den privaten systemeigenen Assemblytyp '*systemeigener_Typ*"|
|[C4710](../error-messages/compiler-warnings/compiler-warning-level-4-c4710.md) (Stufe 4)|"*Funktion*': Funktion nicht inline|
|[C4738](../error-messages/compiler-warnings/compiler-warning-level-3-c4738.md) (Stufe 3)|Das 32-Bit-Gleitkommaergebnis wird im Speicher gespeichert. Möglicherweise kommt es zu einem Leistungsverlust|
|[C4746](../error-messages/compiler-warnings/compiler-warning-c4746.md)|flüchtige Zugriff des "*Ausdruck*" / volatile des unterliegt:\<Iso&#124;ms > festlegen; in Betracht __iso_volatile_load/Store systeminterne Funktionen|
|C4749 (Stufe 4)|bedingt unterstützt: Offsetof auf non-standard-Layout-Typ angewendet "*Typ*"|
|C4767 (Stufe 4)|Name des Abschnitts "*Symbol*' ist länger als 8 Zeichen und wird vom Linker abgeschnitten|
|C4768 (Stufe 3)|__declspec-Attribute vor Verknüpfungsspezifikation werden ignoriert.|
|C4774 (Stufe 4)|"*Zeichenfolge*": im Argument erwartet Formatzeichenfolge *Anzahl* ist kein Zeichenfolgenliteral|
|C4777 (Stufe 4)|"*Funktion*": Formatzeichenfolge "*Zeichenfolge*"erfordert ein Argument des Typs"*Typ1*", sondern Variadic-Argument *Anzahl* weist den Typ "*Typ2*"|
|C4786 (Stufe 3)|"*Symbol*': Objektname wurde abgeschnitten, um"*Anzahl*' Zeichen in den Debuginformationen|
|[C4820](../error-messages/compiler-warnings/compiler-warning-level-4-c4820.md) (Stufe 4)|"*Bytes*'Bytes Abstand hinzugefügten nach dem Konstrukt'*Member_name*"|
|C4826 (Ebene 2)|Konvertierung von '*Typ1*'to'*Typ2*' ist signaturerweitert. Dies kann zu unerwartetem Laufzeitverhalten führen.|
|C4837 (Stufe 4)|Trigraph erkannt: '?? *Zeichen*"ersetzt durch"*Zeichen*"|
|C4841 (Stufe 4)|nicht standardmäßige Erweiterung verwendet: zusammengesetzten Member-Kennzeichner in Offsetof verwendet|
|C4842 (Stufe 4)|Das Ergebnis des "Offsetof" auf einen Typ mit mehrfacher Vererbung angewendet wird nicht garantiert, Compilerversionen konsistent sein.|
|[C4868](../error-messages/compiler-warnings/compiler-warning-c4868.md) (Stufe 4)|"_Datei_(*Line_number*)" Compiler kann die Reihenfolge der Auswertung von links nach rechts in der Initialisierungsliste nicht erzwingen|
|[C4905](../error-messages/compiler-warnings/compiler-warning-level-1-c4905.md) (Stufe 1)|Breites Zeichenfolgenliteral umgewandelt zu "LPSTR"|
|[C4906](../error-messages/compiler-warnings/compiler-warning-level-1-c4906.md) (Stufe 1)|Zeichenfolgenliteral umgewandelt zu "LPWSTR"|
|[C4917](../error-messages/compiler-warnings/compiler-warning-level-1-c4917.md) (Stufe 1)|"*Deklarator*': eine GUID kann nur eine Klasse, Schnittstelle oder Namespace zugeordnet werden|
|[C4928](../error-messages/compiler-warnings/compiler-warning-level-1-c4928.md) (Stufe 1)|Unzulässige Kopierinitialisierung. Mehrere benutzerdefinierte Konvertierungen wurden implizit übernommen|
|[C4931](../error-messages/compiler-warnings/compiler-warning-level-4-c4931.md) (Stufe 4)|Es wird angenommen, dass die Typbibliothek für Anzahl-Bit-Pointer erstellt wurde|
|[C4946](../error-messages/compiler-warnings/compiler-warning-level-1-c4946.md) (Stufe 1)|Reinterpret_cast wird zwischen verknüpften Klassen verwendet: "*class1*'und'*Klasse2*"|
|C4962|"*Funktion*': Profilgesteuerte Optimierungen wurden deaktiviert, da Optimierungen Profildaten Profildaten verursacht hat.|
|[C4986](../error-messages/compiler-warnings/compiler-warning-c4986.md) (Stufe 4)|"*Symbol*': Ausnahmespezifikation stimmt nicht mit der vorherigen Deklaration überein|
|C4987 (Stufe 4)|Es wurde eine nicht standardmäßige Erweiterung verwendet: 'throw (...)'|
|C4988 (Stufe 4)|"*Symbol*': Variable deklariert Bereichs der äußeren Klasse/Funktion|
|C5022|"*Typ*': mehrere bewegungskonstruktoren angegeben|
|C5023|"*Typ*': mehrere Verschiebe-standardzuweisungsoperatoren angegeben|
|C5024 (Stufe 4)|"*Typ*": Verschieben Konstruktor wurde implizit als gelöscht definiert.|
|C5025 (Stufe 4)|"*Typ*': Zuweisungsoperator wurde implizit als gelöscht definiert, verschieben|
|C5026 (Ebene 1 und Stufe 4)|"*Typ*": Verschieben Konstruktor wurde implizit als gelöscht definiert.|
|C5027 (Ebene 1 und Stufe 4)|"*Typ*': Zuweisungsoperator wurde implizit als gelöscht definiert, verschieben|
|C5029 (Stufe 4)|nicht dem Standard entsprechende Erweiterung: Ausrichtungsattribute in C++, Zuweisen von Variablen, Datenmember und Transpondertypen nur|
|C5031 (Stufe 4)|#pragma warning"(POP): wahrscheinlich Konflikt die Folge, in andere Datei abgelegt Status" Warnung "das herunternehmen <sup>14,1</sup>|
|C5032 (Stufe 4)|#pragma warning"(Push) ohne entsprechende #pragma warning"(POP) erkannt <sup>14,1</sup>|
|C5034|Verwenden der systeminternen "*systeminterne*" bewirkt, dass Funktion *Funktion* als Gast-Code kompiliert werden <sup>15.3</sup>|
|C5035|Verwenden der Funktion "*Feature*" bewirkt, dass Funktion *Funktion* als Gast-Code kompiliert werden <sup>15.3</sup>|
|C5036 (Stufe 1)|Beim Kompilieren mit /hybrid:x86arm64-Funktion Varargs zeigerkonvertierung "*Typ1*'to'*Typ2*" <sup>15.3</sup>|
|[C5038](../error-messages/compiler-warnings/c5038.md) (Stufe 4)|Datenmember "*member1*"wird so initialisiert, nach der Datenmember"*member2*" <sup>15.3</sup>|
|C5039 (Stufe 4)|"*Funktion*': Zeiger oder Verweis auf potenziell Auslösen von Funktion" extern "C-Funktion unter - EHc übergeben. Nicht definiertes Verhalten kann auftreten, wenn diese Funktion eine Ausnahme auslöst. <sup>15.5</sup>|
|C5042 (Stufe 3)|"*Funktion*": Funktionsdeklarationen im Gültigkeitsbereich der-Block nicht "Inline" angegeben sein, in standardmäßigem C++ – entfernen "Inlinespezifizierer" <sup>15.5</sup>|

<sup>14,1</sup> diese Warnung ab, die in Visual Studio 2015 Update 1 verfügbar ist.<br>
<sup>14.3</sup> diese Warnung ab, die in Visual Studio 2015 Update 3 verfügbar ist.<br>
<sup>15.3</sup> diese Warnung ist verfügbar in Visual Studio 2017 Version 15.3 ab.<br>
<sup>15.5</sup> diese Warnung ist verfügbar in Visual Studio 2017 Version 15.5 ab.<br>
<sup>Permanent</sup> diese Warnung ist deaktiviert, es sei denn, die [/ liberalen-](../build/reference/permissive-standards-conformance.md) (Compileroption) festgelegt ist.

## <a name="warnings-off-by-default-in-earlier-versions"></a>Warnungen deaktiviert standardmäßig in früheren Versionen

Diese Warnungen wurden deaktiviert standardmäßig in der Compiler vor Visual Studio 2015-Versionen:

|||
|-|-|
|[C4302](../error-messages/compiler-warnings/compiler-warning-level-2-c4302.md) (Ebene 2)|"*Konvertierung*': Verkürzung von '*Typ1*'to'*Typ2*"|
|[C4311](../error-messages/compiler-warnings/compiler-warning-level-1-c4311.md) (Stufe 1)|"*Variable*': zeigerverkürzung von '*Typ*'to'*Typ*"|
|[C4312](../error-messages/compiler-warnings/compiler-warning-level-1-c4312.md) (Stufe 1)|"*Vorgang*': Konvertierung von '*Typ1*'to'*Typ2*" größerem|
|[C4319](../error-messages/compiler-warnings/compiler-warning-level-1-c4319.md) (Stufe 1)|"*Operator*": Null erweitern "*Typ1*'to'*Typ2*" größerem|

Diese Warnung wurde deaktiviert standardmäßig in der Compiler vor Visual Studio 2012-Versionen:

|||
|-|-|
|[C4431](../error-messages/compiler-warnings/compiler-warning-level-4-c4431.md) (Stufe 4)|Fehlender Typspezifizierer - int wird angenommen. Hinweis: default-int wird von C++ nicht unterstützt|

## <a name="see-also"></a>Siehe auch

[warning](../preprocessor/warning.md)
