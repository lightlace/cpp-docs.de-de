---
title: Compilerwarnungen C4800 durch C5999 | Microsoft-Dokumentation
ms.date: 05/30/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4806
- C4807
- C4808
- C4809
- C4810
- C4811
- C4812
- C4813
- C4816
- C4817
- C4822
- C4825
- C4827
- C4837
- C4841
- C4842
- C4843
- C4844
- C4872
- C4880
- C4881
- C4882
- C4900
- C4910
- C4912
- C4913
- C4916
- C4918
- C4920
- C4921
- C4925
- C4926
- C4932
- C4934
- C4935
- C4936
- C4937
- C4938
- C4939
- C4944
- C4947
- C4950
- C4951
- C4952
- C4953
- C4954
- C4955
- C4956
- C4957
- C4958
- C4959
- C4960
- C4961
- C4962
- C4963
- C4966
- C4970
- C4971
- C4972
- C4973
- C4974
- C4981
- C4985
- C4987
- C4988
- C4989
- C4990
- C4991
- C4992
- C4997
- C4998
- C4999
- C5022
- C5023
- C5024
- C5025
- C5026
- C5027
- C5028
- C5029
- C5030
- C5031
- C5032
- C5033
- C5034
- C5035
- C5036
- C5037
- C5039
- C5040
- C5041
- C5042
- C5043
- C5044
dev_langs:
- C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: deee159c9da6fce9001d010a1a6b1db9b3b1d666
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48861420"
---
# <a name="compiler-warnings-c4800-through-c5999"></a>Compilerwarnungen C4800 durch C5999

Die Artikel in diesem Abschnitt der Dokumentation wird erläutert, eine Teilmenge der die Warnmeldungen an, die vom Compiler generiert werden.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="warning-messages"></a>Warnmeldungen

|Warnung|Meldung|
|-------------|-------------|
|[Compilerwarnung (Ebene 3) C4800](compiler-warning-level-3-c4800.md)|"*Typ*': erzwingen Wert auf" bool "" True"oder"False"(leistungswarnung)|
|[Compilerwarnung (Ebene 1) C4803](compiler-warning-level-1-c4803.md)|"*Methode*': Die Raise-Methode verfügt über eine andere Speicherklasse als die des Ereignisses,"*Ereignis*"|
|[Compilerwarnung (Ebene 1) C4804](compiler-warning-level-1-c4804.md)|"*Vorgang*": unsichere Verwendung des Typs "Bool", Vorgang|
|[Compilerwarnung (Ebene 1) C4805](compiler-warning-level-1-c4805.md)|"*Vorgang*": Unsichere Kombination von Typ '*type1*"und Typ"*Typ2*"in Vorgang|
|Compilerwarnung (Stufe 1) C4806|"*Vorgang*': unsicherer Vorgang: kein Wert vom Typ"*type1*"höher gestuften in den Typ"*Typ2*' kann mit die angegebene Konstante übereinstimmen|
|Compilerwarnung (Stufe 1) C4807|"*Vorgang*": Unsichere Kombination von Typ '*type1*"und signiert Bitfeld des Typs"*Typ2*"|
|Compilerwarnung (Stufe 1) C4808|Case "*Wert*' ist kein gültiger Wert für die Switch-Bedingung vom Typ"Bool"|
|Compilerwarnung (Stufe 1) C4809|Switch-Anweisungen enthält redundante "Default"-Bezeichnung; Es werden alle möglichen "Case"-Bezeichnungen angegeben.|
|Compilerwarnung (Stufe 1) C4810|Wert von pragma pack(show) == n|
|Compilerwarnung (Stufe 1) C4811|Wert von 'pragma conform(forScope, show) == Wert'|
|Compilerwarnung (Stufe 1) C4812|Veralteter Deklarationsstil: Verwenden Sie '*New_syntax*"stattdessen|
|Compilerwarnung (Stufe 1) C4813|"*Funktion*': eine Friend-Funktion einer lokalen Klasse muss bereits deklariert|
|Compilerwarnung (Stufe 4) C4816|"*Param*": Parameter hat ein Array der Größe 0 (null), das abgeschnitten wird (es sei denn, die das Objekt als Verweis übergeben wird)|
|Compilerwarnung (Stufe 1) C4817|"*Member*": Unzulässige Verwendung von "." auf diesen Member; Compiler wurde ersetzt durch "->"|
|[Compilerwarnung (Ebene 1) C4819](compiler-warning-level-1-c4819.md)|Die Datei enthält ein Zeichen, das in der aktuellen Codepage (Nummer) nicht dargestellt werden kann. Speichern Sie die Datei im Unicode-Format, um Datenverluste zu verhindern|
|[Compilerwarnung (Ebene 4) C4820](compiler-warning-level-4-c4820.md)|"*Bytes*'Bytes Abstand hinzugefügten nach dem Konstrukt'*Member_name*"|
|[Compilerwarnung (Ebene 1) C4821](compiler-warning-level-1-c4821.md)|Um festzustellen, Unicode-Codierungstyp, speichern Sie die Datei mit Signatur (BOM) nicht möglich.|
|Compilerwarnung (Stufe 1) C4822|"Member Function": Lokale Klassenmemberfunktion keinen Text enthalten.|
|[Compilerwarnung (Ebene 3) C4823](compiler-warning-level-3-c4823.md)|"*Funktion*": verwendet, die feste Zeigern, die Entladesemantik ist aber nicht aktiviert. Erwägen Sie die Verwendung von/EHa|
|Compilerwarnung (Stufe 2) C4826|Konvertierung von '*type1*'to'*Typ2*' ist signaturerweitert. Dies kann zu unerwartetem Laufzeitverhalten führen.|
|Compilerwarnung (Stufe 3) C4827|Eine öffentliche "ToString"-Methode mit 0 Parametern muss als virtuell markiert werden, und überschreiben|
|[Compilerwarnung (Ebene 1) C4829](compiler-warning-level-1-c4829.md)|Möglicherweise falsche Parameter für Main-Funktion. Betrachten Sie ' Int main (Platform:: Array\<Platform:: String ^ > ^ Argv)'|
|[Compilerwarnung (Ebene 1) C4835](compiler-warning-level-1-c4835.md)|"*Variable*': die Initialisierung für exportierte Daten wird nicht ausgeführt werden, bis der ersten Ausführung von verwaltetem Code in die Host-Assembly|
|Compilerwarnung (Stufe 4) C4837|Trigraph gefunden: "?? *Zeichen*"ersetzt durch"*Zeichen*"|
|[Compilerwarnung (Ebene 1) C4838](compiler-warning-level-1-c4838.md)|Konvertierung von '*TYP_1*'to'*TYP_2*"erfordert eine einschränkende Konvertierung|
|[Compilerwarnung (Stufe 3) C4839](compiler-warning-level-3-c4839.md)|nicht standardmäßige Verwendung der Klasse*Typ*"als Argument an eine Variadic-Funktion|
|[Compilerwarnung (Stufe 4) C4840](compiler-warning-level-4-c4840.md)|nicht Portable Verwendung der Klasse*Typ*"als Argument an eine Variadic-Funktion|
|Compilerwarnung (Stufe 4) C4841|nicht standardmäßige Erweiterung verwendet: zusammengesetzter memberkennzeichner in Offsetof verwendeter Bezeichner|
|Compilerwarnung (Stufe 4) C4842|Das Ergebnis von 'Offsetof' wird auf einen Typ mit mehrfacher Vererbung ist nicht garantiert konsistent Compiler-Versionen|
|Compilerwarnung C4843|"*type1*": ein Ausnahmehandler des Verweises zum Array oder Funktionstypen ist nicht erreichbar ist, verwenden Sie '*Typ2*"stattdessen|
|Compilerwarnung C4844|"export Module *Module_name*;" ist jetzt die bevorzugte Syntax zum Deklarieren einer Modulschnittstelle|
|[Compilerwarnung (Stufe 4) C4866](c4866.md)| Erzwingen Compiler möglicherweise nicht die Reihenfolge der Auswertung von links nach rechts für Aufruf *Operatorname*|
|[Compilerwarnung C4867 (Fehler)](compiler-warning-c4867.md)|"*Funktion*': Funktionsaufruf fehlt die Argumentliste; verwenden Sie '*Aufrufen*" um einen Zeiger auf Member zu erstellen.|
|[Compilerwarnung C4868 (Stufe 4)](compiler-warning-c4868.md)|"_Datei_(*Line_number*)" erzwingen Compiler möglicherweise nicht die Reihenfolge der Auswertung von links nach rechts in der Initialisierungsliste|
|Compilerwarnung (Stufe 2) C4872|eine Gleitkommadivision durch Null festgestellt wird, beim Kompilieren des Aufrufdiagramms für: "*Speicherort*"|
|Compilerwarnung (Stufe 1) C4880|Das Umwandeln von "const *TYP_1*'to'*TYP_2*': Umwandeln der Constness einen Zeiger oder Verweis kann zu nicht definiertem Verhalten in einer eingeschränkten Amp-Funktion|
|Compilerwarnung (Stufe 4) C4881|der Konstruktor und/oder der Destruktor wird nicht aufgerufen werden, für die Tile_static-Variable '*Variable*"|
|Compilerwarnung (Stufe 1) C4882|Übergeben von functor-Objekten mit nicht Konstanten aufrufoperatoren an Concurrency:: parallel_for_each ist veraltet.|
|Compilerwarnung C4900|Konflikt zwischen "*tool1*'Version'*version1*'und'*tool2*'Version'*version2*"|
|[Compilerwarnung (Ebene 1) C4905](compiler-warning-level-1-c4905.md)|Breites Zeichenfolgenliteral umgewandelt zu "LPSTR"|
|[Compilerwarnung (Ebene 1) C4906](compiler-warning-level-1-c4906.md)|Zeichenfolgenliteral umgewandelt zu "LPWSTR"|
|Compilerwarnung (Stufe 1) C4910|"\<Bezeichner >:"__declspec(dllexport)"und"Extern"bei einer expliziten Instanziierung nicht miteinander kompatibel sind|
|Compilerwarnung (Stufe 1) C4912|"*Attribut*": Attribut wurde ein nicht definiertes Verhalten für ein geschachteltes UDT|
|Compilerwarnung (Stufe 4) C4913|Benutzerdefinierter binärer Operator "," ist vorhanden, die Überladung konnte aber alle Operanden nicht konvertieren. Es wurde der standardmäßig enthaltene binäre Operator "," verwendet.|
|Compilerwarnung (Stufe 1) C4916|Um einen Dispid "*Beschreibung*": muss eine Schnittstelle eingeführt werden|
|[Compilerwarnung (Ebene 1) C4917](compiler-warning-level-1-c4917.md)|"*Deklarator*': eine GUID kann nur eine Klasse, Schnittstelle oder Namespace zugeordnet werden|
|Compilerwarnung (Stufe 4) C4918|"*Zeichen*": Ungültiges Zeichen in der Pragma-Optimierungsliste|
|Compilerwarnung (Stufe 1) C4920|Enum Enum Members member_1 = value_1, die bereits in Enum-Enumeration als member_2 value_2 =|
|Compilerwarnung (Stufe 3) C4921|"*Beschreibung*": Attribut '*Attribut*' sollte nicht mehrfach angegeben werden|
|Compilerwarnung (Stufe 1) C4925|"*Methode*": Dispinterface-Methode kann nicht von einem Skript aufgerufen werden|
|Compilerwarnung (Stufe 1) C4926|"*Bezeichner*": Symbol ist bereits definiert: Attribute werden ignoriert|
|[Compilerwarnung (Ebene 1) C4927](compiler-warning-level-1-c4927.md)|Unzulässige Konvertierung. mehrere benutzerdefinierte Konvertierungen wurden implizit übernommen.|
|[Compilerwarnung (Ebene 1) C4928](compiler-warning-level-1-c4928.md)|Unzulässige Kopierinitialisierung. Mehrere benutzerdefinierte Konvertierungen wurden implizit übernommen|
|[Compilerwarnung (Ebene 1) C4929](compiler-warning-level-1-c4929.md)|"*Datei*': Typbibliothek enthält eine Union; der Embedded_idl-Qualifizierer wird ignoriert.|
|[Compilerwarnung (Ebene 1) C4930](compiler-warning-level-1-c4930.md)|"*Prototyp*': Funktion mit Prototyp nicht aufgerufen (war eine Variablendefinition gemeint?)|
|[Compilerwarnung (Ebene 4) C4931](compiler-warning-level-4-c4931.md)|Es wird angenommen, dass die Typbibliothek für Anzahl-Bit-Pointer erstellt wurde|
|Compilerwarnung (Stufe 4) C4932|__identifier (*Bezeichner*) und \__bezeichner (*Bezeichner*) sind nicht differenzierbar.|
|Compilerwarnung (Stufe 1) C4934|"__delegate(multicast)" ist veraltet, verwenden Sie '\__delegate "stattdessen|
|Compilerwarnung (Stufe 1) C4935|Assembly-Zugriffsspezifizierer wurde von geändert "*Zugriff*"|
|Compilerwarnung (Ebene 1, Fehler) C4936|__declspec wird nur bei einer Kompilierung mit /clr oder /clr:pure unterstützt.|
|Compilerwarnung (Stufe 4) C4937|"*text1*'und'*" Text2 "*"sind nicht differenzierbar. als Argumente für"*Richtlinie*"|
|Compilerwarnung (Stufe 4) C4938|"*Var*': Reduction-Gleitkommavariable kann dazu führen, dass inkonsistente Ergebnissen bei/fp: strict oder #pragma fenv_access führen|
|Compilerwarnung C4939|#pragma vtordisp ist veraltet und wird in einem der nächsten Releases von Visual C++ entfernt.|
|Compilerwarnung (Stufe 1) C4944|"*Symbol*": Symbol aus kann nicht importiert "*assembly1*': als*Symbol*' ist im aktuellen Bereich bereits vorhanden.|
|[Compilerwarnung (Ebene 1) C4945](compiler-warning-level-1-c4945.md)|"*Symbol*": Symbol aus kann nicht importiert werden kann '*assembly1*": unter*Symbol*'wurde bereits importiert aus einer anderen Assembly'*assembly2* '|
|[Compilerwarnung (Ebene 1) C4946](compiler-warning-level-1-c4946.md)|Reinterpret_cast wird zwischen verknüpften Klassen verwendet: "*class1*'und'*Klasse2*"|
|Compilerwarnung (Stufe 1) C4947|"*Typ_oder_Member*': als veraltet markiert|
|[Compilerwarnung (Ebene 2) C4948](compiler-warning-level-2-c4948.md)|der Rückgabetyp des '*Accessor*' stimmt nicht mit dem letzten Parametertyp des entsprechenden Setters überein|
|[Compilerwarnung (Ebene 1 und Ebene 4) C4949](compiler-warning-level-1-and-level-4-c4949.md)|Pragmas "managed" und "unmanaged" sind sinnvoll, nur bei der Kompilierung mit "/ Clr [: Option]"|
|Compilerwarnung (Ebene 1, Fehler) C4950|"*Typ_oder_Member*': als veraltet markiert|
|Compilerwarnung (Stufe 1) C4951|"*Funktion*" wurde bearbeitet wurde, seit die Profildaten erfasst Daten wurden, funktionsprofildaten werden nicht verwendet|
|Compilerwarnung (Stufe 1) C4952|"*Funktion*": keine Profildaten gefunden wird, in der Programmdatenbank '*PDG-Datei*"|
|Compilerwarnung (Stufe 1) C4953|Inlinee "*Funktion*" wurde bearbeitet wurde, seit die Profildaten erfasst Daten wurden, Profildaten werden nicht verwendet|
|Compilerwarnung C4954|"*Funktion*": keine profilerstellung durchgeführt (enthält Switch-Ausdruck __int64)|
|Compilerwarnung C4955|"*import2*': Import wird ignoriert; wurde bereits importiert aus"*import1*"|
|Compilerwarnung (Ebene 1, Fehler) C4956|"*Typ*': Dieser Typ kann nicht überprüft werden|
|Compilerwarnung (Ebene 1, Fehler) C4957|"*Umwandlung*": explizite Umwandlung von '*Cast_from*'to'*Cast_to*' kann nicht überprüft werden|
|Compilerwarnung (Ebene 1, Fehler) C4958|"*Vorgang*': Zeigerarithmetik kann nicht überprüft werden|
|Compilerwarnung (Ebene 1, Fehler) C4959|keine nicht verwalteten Typ definieren '*Typ*"in/CLR: safe da Zugriff auf seine Member nicht überprüfbaren Code ausgegeben wird|
|Compilerwarnung (Stufe 4) C4960|"*Funktion*' ist zu groß für die profilerstellung|
|Compilerwarnung (Stufe 1) C4961|In 'PGD-Datei' wurden keine Profildaten zusammengeführt, profilgesteuerte Optimierungen werden deaktiviert.|
|Compilerwarnung (Stufe 4) C4962|"*Funktion*': Profilgesteuerte Optimierungen wurden deaktiviert, da die Optimierungen eine Inkonsistenz zwischen den Profildaten verursacht wurde.|
|Compilerwarnung (Stufe 1) C4963|"*Beschreibung*": keine Profildaten gefunden; verschiedene Compileroptionen wurden im instrumentierten Build verwendet.|
|[Compilerwarnung (Ebene 1) C4964](compiler-warning-level-1-c4964.md)|Es wurden keine Optimierungsoptionen angegeben. Informationen zum Unternehmensprofil werden nicht gesammelt werden|
|[Compilerwarnung (Ebene 1) C4965](compiler-warning-level-1-c4965.md)|Implizites Boxing mit ganzer Zahl 0.; Verwenden Sie "nullptr" oder eine explizite Umwandlung|
|Compilerwarnung (Stufe 1) C4966|"*Funktion*' hat eine __code_seg-Anmerkung mit nicht unterstützten Segmentnamen, Anmerkung wird ignoriert.|
|Compilerwarnung C4970|Delegatkonstruktor: Zielobjekt ignoriert, da "*Typ*" ist statisch|
|Compilerwarnung (Stufe 1) C4971|Argumentreihenfolge: \<Zielobjekt >, \<Zielfunktion > für Delegatkonstruktor ist veraltet, verwenden Sie \<Zielfunktion >, \<Zielobjekt = "" >|
|Compilerwarnung (Ebene 1, Fehler) C4972|Das direkte Ändern oder Behandeln des Ergebnisses eines Unboxing-Vorgangs als L-Wert kann nicht überprüft werden.|
|Compilerwarnung (Stufe 1) C4973|"*Symbol*': als veraltet markiert|
|Compilerwarnung (Stufe 1) C4974|"*Symbol*': als veraltet markiert|
|Compilerwarnung (Stufe 3) C4981|Warbird: Funktion "*Funktion*" als __forceinline markierte nicht inline, da sie Ausnahmesemantik enthält|
|Compilerwarnung (Stufe 3) C4985|Symbolname ": Attribute sind in vorheriger Deklaration nicht vorhanden.|
|[Compilerwarnung C4986](compiler-warning-c4986.md)|"*Deklaration*': Ausnahmespezifikation stimmt nicht mit der vorherigen Deklaration überein|
|Compilerwarnung (Stufe 4) C4987|Es wurde eine nicht standardmäßige Erweiterung verwendet: 'throw (...)'|
|Compilerwarnung (Stufe 4) C4988|"*Variable*': Variable, die außerhalb von Klassen-/Funktionsbereichs deklariert|
|Compilerwarnung (Stufe 4) C4989|"*Typ*': Typ aufweist, in Konflikt stehende Definitionen.|
|Compilerwarnung (Stufe 3) C4990|Warbird: *Nachricht*|
|Compilerwarnung (Stufe 3) C4991|Warbird: Funktion "*Funktion*" als __forceinline markierte nicht inline da Schutzstufe des Inlinees größer als das übergeordnete Element ist|
|Compilerwarnung (Stufe 3) C4992|Warbird: Funktion "*Funktion*" als __forceinline markierte nicht inline, da es sich um Inlineassembly enthält, die nicht geschützt werden können|
|[Compilerwarnung (Ebene 3) C4995](compiler-warning-level-3-c4995.md)|"*Funktion*": Name wurde als #pragma als veraltet markiert|
|[Compilerwarnung (Ebene 3) C4996](compiler-warning-level-3-c4996.md)|"*Beschreibung*': *Nachricht*|
|Compilerwarnung (Stufe 1) C4997|"*Klasse*': Co-Klasse implementiert keine COM- oder Pseudoschnittstelle|
|Compilerwarnung (Stufe 1) C4998|Erwartung fehlgeschlagen: *Erwartung*(*Wert*)|
|Compilerwarnung C4999|Unbekannte Warnung wählen Sie den technischen Supportbefehl im Visual C++-Hilfemenü, oder öffnen die Hilfedatei für technischen Support für Weitere Informationen|
|Compilerwarnung C5022|"*Typ*": mehrere bewegungskonstruktoren angegeben|
|Compilerwarnung C5023|"*Typ*": mehrere bewegungszuweisungsoperatoren angegeben|
|Compilerwarnung (Stufe 4) C5024|"*Typ*": Konstruktor wurde implizit als gelöscht definiert.|
|Compilerwarnung (Stufe 4) C5025|"*Typ*': Verschieben der Zuweisungsoperator wurde implizit als gelöscht definiert.|
|Compilerwarnung (Stufe 1 und Stufe 4) C5026|"*Typ*": Konstruktor wurde implizit als gelöscht definiert.|
|Compilerwarnung (Stufe 1 und Stufe 4) C5027|"*Typ*': Verschieben der Zuweisungsoperator wurde implizit als gelöscht definiert.|
|Compilerwarnung (Stufe 1) C5028|"*Namen*': Ausrichtung angegeben wird, in vorheriger Deklaration (*Anzahl*) nicht in Definition angegeben.|
|Compilerwarnung (Stufe 4) C5029|nicht dem Standard entsprechende Erweiterung: Ausrichtungsattribute in C++, die auf Variablen, Datenmember und Tagtypen nur anwenden|
|Compilerwarnung (Stufe 3) C5030|Attribut "*Attribut*" wird nicht erkannt.|
|Compilerwarnung (Stufe 4) C5031|#pragma warning"(POP): wahrscheinlich fehlzuordnung, POP-Warnstatus in anderen Datei mithilfe von Push übertragen|
|Compilerwarnung (Stufe 4) C5032|#pragma warning"(Push) ohne entsprechende #pragma warning"(POP) erkannt|
|Compilerwarnung (Stufe 1) C5033|"*Speicherklassen-*' ist nicht mehr unterstützte Speicherklasse|
|Warnung C5034|Verwenden der systeminternen "*systeminterne*' bewirkt, dass Funktion *Funktion* als gastcode kompiliert.|
|Compilerwarnung C5035|Verwenden des Features "*Feature*' bewirkt, dass Funktion *Funktion* als gastcode kompiliert.|
|Compilerwarnung (Stufe 1) C5036|VarArgs-Funktion zeigerkonvertierung beim Kompilieren mit/Hybrid: x86arm64 "*type1*'to'*Typ2*"|
|Compilerwarnung (Fehler) C5037|"*Memberfunktion*': eine Out-of-Line-Definition eines Members einer Klassenvorlage kann keine Standardargumente|
|[Compilerwarnung (Stufe 4) C5038](c5038.md)|Datenmember "*member1*"wird nach Datenmember initialisiert werden"*member2*"|
|Compilerwarnung (Stufe 4) C5039|"*Funktion*': Zeiger oder Verweis auf die möglicherweise auslösende Funktion übergeben" extern "C-Funktion unter - EHc übergeben. Nicht definiertes Verhalten kann auftreten, wenn diese Funktion eine Ausnahme auslöst.|
|Compilerwarnung (Stufe 3) C5040|Dynamische Ausnahmespezifikationen gelten nur in C ++ 14 und früher; zum Behandeln von als noexcept(false) zurückgibt|
|Compilerwarnung (Stufe 1) C5041|"*Definition*': Out-of-Line-Definition für statischen Constexpr-Datenmember ist nicht erforderlich, und ist in C ++ 17 veraltet|
|Compilerwarnung (Stufe 3) C5042|"*Deklaration*": Funktionsdeklarationen im Blockbereich können nicht "Inline" angegeben werden, in Standard-c++, entfernen Sie 'Inline'-Spezifizierer|
|Compilerwarnung (Stufe 2) C5043|"*Spezifikation*': Ausnahmespezifikation stimmt nicht mit der vorherigen Deklaration überein|
|Compilerwarnung (Stufe 4) C5044|Ein Argument für die Befehlszeilenoption *Option* zeigt auf einen Pfad "*Pfad*' nicht vorhanden|
|[Compilerwarnung C5045](c5045.md)|Compilerfehler fügt Spectre-Entschärfung, Auslastung des Arbeitsspeichers angegeben, wenn "/ qspectre" wechseln|
