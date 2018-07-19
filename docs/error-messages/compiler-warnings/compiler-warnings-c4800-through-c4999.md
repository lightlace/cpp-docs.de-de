---
title: Compilerfehler Warnungen C4800 über C5999 | Microsoft Docs
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
- C4840
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
ms.openlocfilehash: d5fb04d31451ac4c49a0a2c11a3699b8a670a6c4
ms.sourcegitcommit: e013acba70aa29fed60ae7945162adee23e19c3b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2018
ms.locfileid: "36322331"
---
# <a name="compiler-warnings-c4800-through-c5999"></a>Compilerfehler Warnungen C4800 über C5999

Die Artikel in diesem Abschnitt der Dokumentation wird erläutert, eine Teilmenge der warnungsmeldungen, die vom Compiler generiert werden.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="warning-messages"></a>Warnmeldungen

|Warnung|Meldung|
|-------------|-------------|
|[Compilerwarnung (Ebene 3) C4800](compiler-warning-level-3-c4800.md)|"*Typ*": erzwungen wird Wert Bool 'True' oder 'False' (Leistung Warnung)|
|[Compilerwarnung (Ebene 1) C4803](compiler-warning-level-1-c4803.md)|"*Methode*': Die Raise-Methode wurde eine anderen Speicherklasse aus, der das Ereignis"*Ereignis*"|
|[Compilerwarnung (Ebene 1) C4804](compiler-warning-level-1-c4804.md)|"*Vorgang*': unsichere Verwendung des Typs"Bool", Vorgang|
|[Compilerwarnung (Ebene 1) C4805](compiler-warning-level-1-c4805.md)|"*Vorgang*": Unsichere Kombination von Typ '*Typ1*"und Typ"*Typ2*"im Vorgang|
|Compilerwarnung (Stufe 1) C4806|"*Vorgang*': unsichere Operation: kein Wert vom Typ"*Typ1*"höher gestuften in den Typ"*Typ2*"kann der angegebenen Konstante übereinstimmen|
|Compilerwarnung (Stufe 1) C4807|"*Vorgang*": Unsichere Kombination von Typ '*Typ1*"und signiert Bitfeld des Typs"*Typ2*"|
|Compilerwarnung (Stufe 1) C4808|Anfrage "*Wert*' ist kein gültiger Wert für Switch-Bedingung vom Typ"Bool"|
|Compilerwarnung (Stufe 1) C4809|Switch-Anweisung verfügt über redundante 'Default' Bezeichnung; alle möglichen 'Case'-Beschriftungen wurden angegeben|
|Compilerwarnung (Stufe 1) C4810|Wert von pragma pack(show) == n|
|Compilerwarnung (Stufe 1) C4811|Wert von 'pragma conform(forScope, show) == Wert'|
|Compilerwarnung (Stufe 1) C4812|Veralteter Deklarationsstil: Verwenden Sie "*New_syntax*" stattdessen|
|Compilerwarnung (Stufe 1) C4813|"*Funktion*': eine Friend-Funktion einer lokalen Klasse muss bereits deklariert|
|Compilerwarnung (Stufe 4) C4816|"*Param*': Parameter hat ein Array der Größe 0 (null), das abgeschnitten wird (es sei denn, das Objekt als Verweis übergeben wird)|
|Compilerwarnung (Stufe 1) C4817|"*Member*': Unzulässige Verwendung von". "auf diesen Member; Compiler wurde ersetzt durch"->"|
|[Compilerwarnung (Ebene 1) C4819](compiler-warning-level-1-c4819.md)|Die Datei enthält ein Zeichen, das in der aktuellen Codepage (Nummer) nicht dargestellt werden kann. Speichern Sie die Datei im Unicode-Format, um Datenverluste zu vermeiden|
|[Compilerwarnung (Ebene 4) C4820](compiler-warning-level-4-c4820.md)|"*Bytes*'Bytes Abstand hinzugefügten nach dem Konstrukt'*Member_name*"|
|[Compilerwarnung (Ebene 1) C4821](compiler-warning-level-1-c4821.md)|Kann nicht zum Ermitteln von Unicode-Codierungstyp, speichern Sie die Datei mit Signatur (BOM)|
|Compilerwarnung (Stufe 1) C4822|"Member Function": Lokale Klassenmemberfunktion keinen Text enthalten.|
|[Compilerwarnung (Ebene 3) C4823](compiler-warning-level-3-c4823.md)|"*Funktion*': verwendet, die feste Zeiger, aber entladen nicht aktiviert. Erwägen Sie/EHa|
|Compilerwarnung (Stufe 2) C4826|Konvertierung von '*Typ1*'to'*Typ2*' ist signaturerweitert. Dies kann zu unerwartetem Laufzeitverhalten führen.|
|Compilerwarnung (Stufe 3) C4827|Eine öffentliche Methode von "ToString" mit 0-Parametern als virtuell gekennzeichnet werden, und überschreiben|
|[Compilerwarnung (Ebene 1) C4829](compiler-warning-level-1-c4829.md)|Möglicherweise falsche Parameter für Main-Funktion. Betrachten Sie ' Int main (Platform:: Array\<Platform:: String ^ > ^ Argv)'|
|[Compilerwarnung (Ebene 1) C4835](compiler-warning-level-1-c4835.md)|"*Variable*": Initialisierer für die exportierten Daten wird nicht ausgeführt werden, bis verwalteter Code in der Hostassembly zuerst ausgeführt wird|
|Compilerwarnung (Stufe 4) C4837|Trigraph erkannt: '?? *Zeichen*"ersetzt durch"*Zeichen*"|
|[Compilerwarnung (Ebene 1) C4838](compiler-warning-level-1-c4838.md)|Konvertierung von '*TYP_1*'to'*TYP_2*"ist eine einschränkende Konvertierung erforderlich|
|[Compilerwarnung (Stufe 3) C4839](compiler-warning-level-3-c4839.md)|nicht standardmäßige Verwendung der Klasse*Typ*"als Argument an eine Variadic-Funktion|
|Compilerwarnung (Stufe 4) C4840|nicht Portable verwenden der Klasse*Typ*"als Argument an eine Variadic-Funktion|
|Compilerwarnung (Stufe 4) C4841|nicht standardmäßige Erweiterung verwendet: zusammengesetzten Member-Kennzeichner in Offsetof verwendet|
|Compilerwarnung (Stufe 4) C4842|Das Ergebnis des "Offsetof" auf einen Typ mit mehrfacher Vererbung angewendet wird nicht garantiert, Compilerversionen konsistent sein.|
|Compilerwarnung C4843|"*Typ1*": ein Ausnahmehandler eines Verweises auf Array- oder Funktionsausdruck Typ ist nicht erreichbar, verwenden Sie "*Typ2*" stattdessen|
|Compilerwarnung C4844|"Exportieren Modul *Modulname*;" ist jetzt die bevorzugte Syntax zum Deklarieren einer Modul-Schnittstelle|
|[Compilerwarnung C4867 (Fehler)](compiler-warning-c4867.md)|"*Funktion*': Funktionsaufruf fehlt die Argumentliste; verwenden Sie"*Aufrufen*"So erstellen einen Zeiger auf Member|
|[Compilerwarnung (Stufe 4) C4868](compiler-warning-c4868.md)|"_Datei_(*Line_number*)" Compiler kann die Reihenfolge der Auswertung von links nach rechts in der Initialisierungsliste nicht erzwingen|
|Compilerwarnung (Stufe 2) C4872|Floating Point Division durch 0 (null), die beim Kompilieren des Aufrufdiagramms für das Concurrency:: parallel_for_each am erkannt: '*Speicherort*"|
|Compilerwarnung (Stufe 1) C4880|Umwandlung von ' const *TYP_1*'to'*TYP_2*": Umwandeln von einem Zeiger oder Verweis Constness möglicherweise zu nicht definiertem Verhalten in einer eingeschränkten Amp-Funktion|
|Compilerwarnung (Stufe 4) C4881|des Konstruktors und/oder des Destruktors wird nicht aufgerufen werden, für die "tile_static" Variable "*Variable*"|
|Compilerwarnung (Stufe 1) C4882|übergeben Funktionselemente mit Operatoren nicht Const-Aufruf an Concurrency:: parallel_for_each ist veraltet.|
|Compilerwarnung C4900|Konflikt zwischen "*tool1*"Version"*version1*'und'*tool2*"Version"*version2*"|
|[Compilerwarnung (Ebene 1) C4905](compiler-warning-level-1-c4905.md)|Breites Zeichenfolgenliteral umgewandelt zu "LPSTR"|
|[Compilerwarnung (Ebene 1) C4906](compiler-warning-level-1-c4906.md)|Zeichenfolgenliteral umgewandelt zu "LPWSTR"|
|Compilerwarnung (Stufe 1) C4910|"\<Bezeichner >:"__declspec(dllexport)"und"Extern"sind bei einer expliziten Instanziierung nicht kompatibel|
|Compilerwarnung (Stufe 1) C4912|"*Attribut*": Attribut weist ein nicht definiertes Verhalten für ein geschachteltes UDT|
|Compilerwarnung (Stufe 4) C4913|Benutzerdefinierter binärer Operator "," ist vorhanden, die Überladung konnte aber alle Operanden nicht konvertieren. Es wurde der standardmäßig enthaltene binäre Operator "," verwendet.|
|Compilerwarnung (Stufe 1) C4916|Um einen Dispid haben "*Beschreibung*': eine Schnittstelle eingeführt werden müssen|
|[Compilerwarnung (Ebene 1) C4917](compiler-warning-level-1-c4917.md)|"*Deklarator*': eine GUID kann nur eine Klasse, Schnittstelle oder ein Namespace zugeordnet werden|
|Compilerwarnung (Stufe 4) C4918|"*Zeichen*': Ungültiges Zeichen in der Pragma-Optimierungsliste|
|Compilerwarnung (Stufe 1) C4920|Enum Enum Member member_1 = value_1, die bereits in der Enum-enumerarion als member_2 = value_2|
|Compilerwarnung (Stufe 3) C4921|"*Beschreibung*":-Attributwert "*Attribut*" sollte nicht mehrfach angegeben werden|
|Compilerwarnung (Stufe 1) C4925|"*Methode*': Dispinterface-Methode kann nicht aus einem Skript aufgerufen werden|
|Compilerwarnung (Stufe 1) C4926|"*Bezeichner*": Symbol ist bereits definiert: Attribute werden ignoriert|
|[Compilerwarnung (Ebene 1) C4927](compiler-warning-level-1-c4927.md)|Unzulässige Konvertierung. mehrere benutzerdefinierte Konvertierungen wurden implizit übernommen.|
|[Compilerwarnung (Ebene 1) C4928](compiler-warning-level-1-c4928.md)|Unzulässige Kopierinitialisierung. Mehrere benutzerdefinierte Konvertierungen wurden implizit übernommen|
|[Compilerwarnung (Ebene 1) C4929](compiler-warning-level-1-c4929.md)|"*Datei*": Typbibliothek enthält eine Union; den Qualifizierer 'Embedded_idl' ignorieren|
|[Compilerwarnung (Ebene 1) C4930](compiler-warning-level-1-c4930.md)|"*Prototyp*': Funktion mit Prototyp nicht aufgerufen (war eine Variablendefinition vorgesehen?)|
|[Compilerwarnung (Ebene 4) C4931](compiler-warning-level-4-c4931.md)|Es wird angenommen, dass die Typbibliothek für Anzahl-Bit-Pointer erstellt wurde|
|Compilerwarnung (Stufe 4) C4932|__identifier (*Bezeichner*) und \__identifier (*Bezeichner*) sind nicht differenzierbar.|
|Compilerwarnung (Stufe 1) C4934|"__delegate(multicast)" ist veraltet, verwenden Sie "\__delegate" stattdessen|
|Compilerwarnung (Stufe 1) C4935|Assembly-Zugriffsspezifizierer geändert von "*Zugriff*"|
|Compilerwarnung (Stufe 1, Fehler) C4936|__declspec wird nur bei einer Kompilierung mit /clr oder /clr:pure unterstützt.|
|Compilerwarnung (Stufe 4) C4937|"*text1*'und'*" Text2 "*"sind nicht als Argumente für"*Richtlinie*"|
|Compilerwarnung (Stufe 4) C4938|"*Var*": Reduction-Gleitkommavariable kann dazu führen, dass inkonsistente Ergebnissen bei/fp: strict oder #pragma fenv_access führen|
|Compilerwarnung C4939|#pragma vtordisp ist veraltet und wird in einem der nächsten Releases von Visual C++ entfernt.|
|Compilerwarnung (Stufe 1) C4944|"*Symbol*": Symbol aus kann nicht importiert "*assembly1*': als*Symbol*" ist bereits im aktuellen Bereich vorhanden.|
|[Compilerwarnung (Ebene 1) C4945](compiler-warning-level-1-c4945.md)|"*Symbol*": kann nicht importiert Symbol aus "*assembly1*': als*Symbol*'wurde bereits importiert aus einer anderen Assembly'*assembly2* '|
|[Compilerwarnung (Ebene 1) C4946](compiler-warning-level-1-c4946.md)|Reinterpret_cast wird zwischen verknüpften Klassen verwendet: "*class1*'und'*Klasse2*"|
|Compilerwarnung (Stufe 1) C4947|"*Type_or_member*': als veraltet markiert|
|[Compilerwarnung (Ebene 2) C4948](compiler-warning-level-2-c4948.md)|Rückgabetyp "*Accessor*" entspricht nicht den letzten Parametertyp der entsprechenden Setter-Methode|
|[Compilerwarnung (Ebene 1 und Ebene 4) C4949](compiler-warning-level-1-and-level-4-c4949.md)|Pragmas "managed" und "nicht verwaltet" sind sinnvoll, nur beim Kompilieren mit "/ Clr [: Option]"|
|Compilerwarnung (Stufe 1, Fehler) C4950|"*Type_or_member*': als veraltet markiert|
|Compilerwarnung (Stufe 1) C4951|"*Funktion*" wurde bearbeitet, seit die Profildaten Daten erfasst wurden, funktionsprofildaten werden nicht verwendet.|
|Compilerwarnung (Stufe 1) C4952|"*Funktion*': keine Profildaten gefunden wird, in der Programmdatenbank '*Pgd_file*"|
|Compilerwarnung (Stufe 1) C4953|Inlinee "*Funktion*" wurde bearbeitet, seit die Profildaten Daten erfasst wurden, nicht verwendet Profildaten|
|Compilerwarnung C4954|"*Funktion*": ein Profil nicht erstellt (__int64 Schalterausdruck enthält)|
|Compilerwarnung C4955|"*import2*': Import wird ignoriert; bereits importiert aus"*import1*"|
|Compilerwarnung (Stufe 1, Fehler) C4956|"*Typ*': Dieser Typ ist nicht überprüfbar|
|Compilerwarnung (Stufe 1, Fehler) C4957|"*Umwandlung*": explizite Umwandlung von '*Cast_from*'to'*Cast_to*"ist nicht überprüfbar|
|Compilerwarnung (Stufe 1, Fehler) C4958 generiert|"*Vorgang*': Zeigerarithmetik ist nicht überprüfbar|
|Compilerwarnung (Stufe 1, Fehler) C4959|keine nicht verwalteten Typ definieren "*Typ*" in/CLR: safe, da nicht überprüfbaren Code den Zugriff auf ihre Member ausgegeben wird.|
|Compilerwarnung (Stufe 4) C4960|"*Funktion*" ist zu groß, um ein Profil|
|Compilerwarnung (Stufe 1) C4961|In 'PGD-Datei' wurden keine Profildaten zusammengeführt, profilgesteuerte Optimierungen werden deaktiviert.|
|Compilerwarnung (Stufe 4) C4962|"*Funktion*': Profilgesteuerte Optimierungen wurden deaktiviert, da Optimierungen Profildaten Profildaten verursacht hat.|
|Compilerwarnung (Stufe 1) C4963|"*Beschreibung*': keine Profildaten"; "ist in den instrumentierten Build verschiedene Compileroptionen verwendet wurden|
|[Compilerwarnung (Ebene 1) C4964](compiler-warning-level-1-c4964.md)|Es wurden keine Optimierungsoptionen angegeben. Profilinformationen werden nicht gesammelt werden|
|[Compilerwarnung (Ebene 1) C4965](compiler-warning-level-1-c4965.md)|Implizites Feld der Ganzzahl 0; Nullptr oder explizite Typumwandlung verwenden|
|Compilerwarnung (Stufe 1) C4966|"*Funktion*" __code_seg Anmerkung mit nicht unterstützten Segmentnamen Anmerkung ignoriert hat|
|Compilerwarnung C4970|Delegatkonstruktor: Zielobjekt ignoriert, da "*Typ*" ist statisch|
|Compilerwarnung (Stufe 1) C4971|Argument Order: \<Zielobjekt >, \<Funktion als Ziel > für Delegatkonstruktor veraltet ist, verwenden Sie \<Ziel Funktion >, \<Zielobjekt = "" >|
|Compilerwarnung (Stufe 1, Fehler) C4972|Das direkte Ändern oder Behandeln des Ergebnisses eines Unboxing-Vorgangs als L-Wert kann nicht überprüft werden.|
|Compilerwarnung (Stufe 1) C4973|"*Symbol*': als veraltet markiert|
|Compilerwarnung (Stufe 1) C4974|"*Symbol*': als veraltet markiert|
|Compilerwarnung (Stufe 3) C4981|Warbird: Funktion "*Funktion*" als __forceinline markiert nicht inline, da sie die Semantik der Ausnahme enthält|
|Compilerwarnung (Stufe 3) C4985|Symbolname ": Attribute in vorheriger Deklaration nicht vorhanden sind.|
|[Compilerwarnung C4986](compiler-warning-c4986.md)|"*Deklaration*': Ausnahmespezifikation stimmt nicht mit der vorherigen Deklaration überein|
|Compilerwarnung (Stufe 4) C4987|Es wurde eine nicht standardmäßige Erweiterung verwendet: 'throw (...)'|
|Compilerwarnung (Stufe 4) C4988|"*Variable*': Variable deklariert Bereichs der äußeren Klasse/Funktion|
|Compilerwarnung (Stufe 4) C4989|"*Typ*': Typ verfügt über in Konflikt stehende Definitionen.|
|Compilerwarnung (Stufe 3) C4990|Warbird: *Nachricht*|
|Compilerwarnung (Stufe 3) C4991|Warbird: Funktion "*Funktion*" als "__forceinline" nicht inline Schutzebene des Inlinees: größer als das übergeordnete Element ist markiert|
|Compilerwarnung (Stufe 3) C4992|Warbird: Funktion "*Funktion*" als __forceinline markiert nicht inline, da es sich um Inlineassembly enthält, der nicht geschützt werden können|
|[Compilerwarnung (Ebene 3) C4995](compiler-warning-level-3-c4995.md)|"*Funktion*": Name wurde als veraltet #pragma markiert|
|[Compilerwarnung (Ebene 3) C4996](compiler-warning-level-3-c4996.md)|"*Beschreibung*": *Nachricht*|
|Compilerwarnung (Stufe 1) C4997|"*Klasse*': Coclass implementiert keine COM- oder Pseudoschnittstelle|
|Compilerwarnung (Stufe 1) C4998|Erwartung fehlgeschlagen: *Annahme*(*Wert*)|
|Compilerwarnung C4999|Unbekannte Warnung wählen Sie den technischen Supportbefehl im Visual C++-Hilfemenü, oder öffnen Sie den technischen Support-Hilfedatei für Weitere Informationen|
|Compilerwarnung C5022|"*Typ*': mehrere bewegungskonstruktoren angegeben|
|Compilerwarnung C5023|"*Typ*': mehrere Verschiebe-standardzuweisungsoperatoren angegeben|
|Compilerwarnung (Stufe 4) C5024|"*Typ*": Verschieben Konstruktor wurde implizit als gelöscht definiert.|
|Compilerwarnung (Stufe 4) C5025|"*Typ*': Zuweisungsoperator wurde implizit als gelöscht definiert, verschieben|
|Compilerwarnung (Stufe 1 und Stufe 4) C5026|"*Typ*": Verschieben Konstruktor wurde implizit als gelöscht definiert.|
|Compilerwarnung (Stufe 1 und Stufe 4) C5027|"*Typ*': Zuweisungsoperator wurde implizit als gelöscht definiert, verschieben|
|Compilerwarnung (Stufe 1) C5028|"*Namen*': Ausrichtung angegeben, in der vorherigen Deklaration (*Anzahl*) nicht in der Definition angegeben.|
|Compilerwarnung (Stufe 4) C5029|nicht dem Standard entsprechende Erweiterung: Ausrichtungsattribute in C++, Zuweisen von Variablen, Datenmember und Transpondertypen nur|
|Compilerwarnung (Stufe 3) C5030|Attribut "*Attribut*" wird nicht erkannt.|
|Compilerwarnung (Stufe 4) C5031|#pragma warning"(POP): wahrscheinlich Konflikt die Folge, herunternehmen Status" Warnung "in anderen Datei abgelegt|
|Compilerwarnung (Stufe 4) C5032|#pragma warning"(Push) ohne entsprechende #pragma warning"(POP) erkannt|
|Compilerwarnung (Stufe 1) C5033|"*speicherklassenattribute*" ist nicht mehr unterstützte Speicherklasse|
|Compilerwarnung C5034|Verwenden der systeminternen "*systeminterne*" bewirkt, dass Funktion *Funktion* als Gast-Code kompiliert werden|
|Compilerwarnung C5035|Verwenden der Funktion "*Feature*" bewirkt, dass Funktion *Funktion* als Gast-Code kompiliert werden|
|Compilerwarnung (Stufe 1) C5036|Beim Kompilieren mit /hybrid:x86arm64-Funktion Varargs zeigerkonvertierung "*Typ1*'to'*Typ2*"|
|Compilerwarnung (Fehler) C5037|"*Memberfunktion*': eine Out-of-Line-Definition eines Elements einer Klassenvorlage sind keine Standardargumente|
|[Compilerwarnung (Stufe 4) C5038](c5038.md)|Datenmember "*member1*"wird so initialisiert, nach der Datenmember"*member2*"|
|Compilerwarnung (Stufe 4) C5039|"*Funktion*': Zeiger oder Verweis auf potenziell Auslösen von Funktion" extern "C-Funktion unter - EHc übergeben. Nicht definiertes Verhalten kann auftreten, wenn diese Funktion eine Ausnahme auslöst.|
|Compilerwarnung (Stufe 3) C5040|Dynamische Ausnahmespezifikationen sind gültig, nur in C ++ 14 und früheren Versionen. zum Behandeln von als noexcept(false)|
|Compilerwarnung (Stufe 1) C5041|"*Definition*": Out-of-Line-Definition für Constexpr statischer Datenmember ist nicht erforderlich und veraltetes Feature in C ++ 17|
|Compilerwarnung (Stufe 3) C5042|"*Deklaration*": Funktionsdeklarationen im Gültigkeitsbereich der-Block nicht "Inline" angegeben sein, in standardmäßigem C++ – "Inlinespezifizierer" entfernen|
|Compilerwarnung (Stufe 2) C5043|"*Spezifikation*': Ausnahmespezifikation stimmt nicht mit der vorherigen Deklaration überein|
|Compilerwarnung (Stufe 4) C5044|Ein Argument an die Befehlszeilenoption *Option* verweist auf einen Pfad "*Pfad*", nicht vorhanden|
|[Compilerwarnung C5045](c5045.md)|Compilerfehler wird Absorptionsspektrum Entschärfung einfügen, Arbeitsspeicherlast angegeben, wenn /Qspectre wechseln|
