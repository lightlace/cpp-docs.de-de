---
title: "Compilerfehler Warnungen C4800 über C5999 | Microsoft Docs"
ms.date: 10/25/2017
ms.technology: cpp-tools
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
- C5038
dev_langs: C++
ms.assetid: c3182430-8b3b-4ab2-a532-5cd436707dc8
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1bf919fbb1959af6fad031a7f32262466f6f49ff
ms.sourcegitcommit: 69632887f7a85f4841c49b4c1353d3144927a52c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2017
---
# <a name="compiler-warnings-c4800-through-c5999"></a>Compilerfehler Warnungen C4800 über C5999

In die Artikeln in diesem Teil der Dokumentation enthalten Informationen über eine Teilmenge von Visual C++-Compiler-Warnungen. Sie können die Informationen hier aufrufen oder, im Ausgabefenster in Visual Studio, können Sie eine Fehlernummer auswählen und dann die F1-Taste drücken.

> [!NOTE]
> Nicht jeder [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] Fehler oder eine Warnung in MSDN dokumentiert ist. In vielen Fällen enthält die diagnosemeldung alle Informationen, die verfügbar ist. Wenn Sie der Meinung sind, dass eine Fehlermeldung einer zusätzlichen Erklärung bedarf, informieren Sie uns bitte. Verwenden Sie die Feedback-Formular auf dieser Seite, oder wechseln Sie auf der Menüleiste in Visual Studio und wählen Sie **Hilfe**, **Melden eines Fehlers**, oder Sie können einen Bericht Vorschlag oder Fehler senden, auf [Microsoft Connect](http://connect.microsoft.com/VisualStudio).

Sie möglicherweise zusätzliche Unterstützung für Fehler und Warnungen für den öffentlichen Foren von MSDN. Die [Visual C++-Sprache](http://go.microsoft.com/fwlink/?LinkId=158195) Forum eignet sich für Fragen und Diskussionen zu den [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] -Sprachsyntax und -Compiler. Die [Visual C++ Allgemein](http://go.microsoft.com/fwlink/?LinkId=158194) Forum eignet sich für Fragen zum [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] , die in anderen Foren nicht diskutiert werden. Sie können auch Hilfe zu Fehlern und Warnungen finden, auf [Stack Overflow](http://stackoverflow.com/).

## <a name="in-this-section"></a>In diesem Abschnitt

|Warnung|Meldung|
|-------------|-------------|
|[Compilerwarnung (Ebene 3) C4800](compiler-warning-level-3-c4800.md)|'Typ': erzwungen wird Wert Bool 'True' oder 'False' (Leistung Warnung)|
|[Compilerwarnung (Ebene 1) C4803](compiler-warning-level-1-c4803.md)|'Methode': Die Raise-Methode wurde eine anderen Speicherklasse aus, der das Ereignis 'Ereignis'|
|[Compilerwarnung (Ebene 1) C4804](compiler-warning-level-1-c4804.md)|'Operation': unsichere Verwendung des Typs "Bool", Vorgang|
|[Compilerwarnung (Ebene 1) C4805](compiler-warning-level-1-c4805.md)|'Operation': Unsichere Kombination von Typ 'Typ' mit Typ "Typ" in-Vorgang|
|Compilerwarnung (Stufe 1) C4806|'Operation': unsichere Operation: kein Wert vom Typ "Typ" Typ "type" höher gestuft, kann der angegebenen Konstante übereinstimmen|
|Compilerwarnung (Stufe 1) C4807|'Operation': Unsichere Kombination von Typ "Typ" und signiertem Bitfeld des Typs "Typ"|
|Compilerwarnung (Stufe 1) C4808|Case 'Wert' ist kein gültiger Wert für Switch-Bedingung vom Typ "Bool"|
|Compilerwarnung (Stufe 1) C4809|Switch-Anweisung verfügt über redundante 'Default' Bezeichnung; alle möglichen 'Case'-Beschriftungen wurden angegeben|
|Compilerwarnung (Stufe 1) C4810|Wert von pragma pack(show) == n|
|Compilerwarnung (Stufe 1) C4811|Wert von 'pragma conform(forScope, show) == Wert'|
|Compilerwarnung (Stufe 1) C4812|Veralteter Deklarationsstil: Verwenden Sie stattdessen „new_syntax“.|
|Compilerwarnung (Stufe 1) C4813|'Funktion': eine Friend-Funktion einer lokalen Klasse muss bereits deklariert|
|Compilerwarnung (Stufe 4) C4816|'Param': Parameter hat ein Array der Größe 0 (null), das abgeschnitten wird (es sei denn, das Objekt als Verweis übergeben wird)|
|Compilerwarnung (Stufe 1) C4817|'Member': Unzulässige Verwendung von "." auf diesen Member. Compilerfehler ersetzt durch "->"|
|[Compilerwarnung (Ebene 1) C4819](compiler-warning-level-1-c4819.md)|Die Datei enthält ein Zeichen, das in der aktuellen Codepage (Nummer) nicht dargestellt werden kann. Speichern Sie die Datei im Unicode-Format, um Datenverluste zu vermeiden|
|[Compilerwarnung (Ebene 4) C4820](compiler-warning-level-4-c4820.md)|'Bytes' Bytes Abstand nach dem Konstrukt 'member_name'|
|[Compilerwarnung (Ebene 1) C4821](compiler-warning-level-1-c4821.md)|Kann nicht zum Ermitteln von Unicode-Codierungstyp, speichern Sie die Datei mit Signatur (BOM)|
|Compilerwarnung (Stufe 1) C4822|"Member Function": Lokale Klassenmemberfunktion keinen Text enthalten.|
|[Compilerwarnung (Ebene 3) C4823](compiler-warning-level-3-c4823.md)|'Funktion': verwendet, die feste Zeiger, aber entladen nicht aktiviert. Erwägen Sie/EHa|
|Compilerwarnung (Stufe 2) C4826|Konvertierung von '*Typ1*'to'*Typ2*' ist signaturerweitert. Dies kann zu unerwartetem Laufzeitverhalten führen.|
|Compilerwarnung (Stufe 3) C4827|Eine öffentliche Methode von "ToString" mit 0-Parametern als virtuell gekennzeichnet werden, und überschreiben|
|[Compilerwarnung (Ebene 1) C4829](compiler-warning-level-1-c4829.md)|Möglicherweise falsche Parameter für Main-Funktion. Betrachten Sie ' Int main (Platform:: Array\<Platform:: String ^ > ^ Argv)'|
|[Compilerwarnung (Ebene 1) C4835](compiler-warning-level-1-c4835.md)|'Variable': die Initialisierung für die exportierten Daten wird nicht ausgeführt, bis verwalteter Code in der Hostassembly zuerst ausgeführt wird|
|Compilerwarnung (Stufe 4) C4837|Trigraph erkannt: '?? *Zeichen*"ersetzt durch"*Zeichen*"|
|[Compilerwarnung (Ebene 1) C4838](compiler-warning-level-1-c4838.md)|Konvertierung von 'type_1' zu 'type_2' ist eine einschränkende Konvertierung erforderlich.|
|[Compilerwarnung (Stufe 3) C4839](compiler-warning-level-3-c4839.md)|nicht standardmäßige Verwendung der Klasse*Typ*"als Argument an eine Variadic-Funktion|
|Compilerwarnung (Stufe 4) C4840|nicht Portable verwenden der Klasse*Typ*"als Argument an eine Variadic-Funktion|
|Compilerwarnung (Stufe 4) C4841|nicht standardmäßige Erweiterung verwendet: zusammengesetzten Member-Kennzeichner in Offsetof verwendet|
|Compilerwarnung (Stufe 4) C4842|Das Ergebnis des "Offsetof" auf einen Typ mit mehrfacher Vererbung angewendet wird nicht garantiert, Compilerversionen konsistent sein.|
|[Compilerwarnung C4867 (Fehler)](compiler-warning-c4867.md)|'Funktion': Funktionsaufruf fehlt die Argumentliste. Verwenden Sie "Aufruf" So erstellen einen Zeiger auf member|
|[Compilerwarnung (Stufe 4) C4868](compiler-warning-c4868.md)|"_Datei_(*Line_number*)" Compiler kann die Reihenfolge der Auswertung von links nach rechts in der Initialisierungsliste nicht erzwingen|
|Compilerwarnung (Stufe 2) C4872|Floating Point Division durch 0 (null), die beim Kompilieren des Aufrufdiagramms für das Concurrency:: parallel_for_each am erkannt: '*Speicherort*"|
|Compilerwarnung (Stufe 1) C4880|Umwandlung von 'const type_1' zu 'type_2': Umwandlung von einem Zeiger oder Verweis Constness möglicherweise zu nicht definiertem Verhalten in einer eingeschränkten Amp-Funktion|
|Compilerwarnung (Stufe 4) C4881|der Konstruktor und/oder des Destruktors wird nicht für "tile_static"-Variable 'Variable' aufgerufen werden|
|Compilerwarnung (Stufe 1) C4882|übergeben Funktionselemente mit Operatoren nicht Const-Aufruf an Concurrency:: parallel_for_each ist veraltet.|
|Compilerwarnung C4900|Konflikt zwischen "tool1" Version "version1" und "tool2" Version "version2"|
|[Compilerwarnung (Ebene 1) C4905](compiler-warning-level-1-c4905.md)|
          Breites Zeichenfolgenliteral umgewandelt zu "LPSTR"|
|[Compilerwarnung (Ebene 1) C4906](compiler-warning-level-1-c4906.md)|
          Zeichenfolgenliteral umgewandelt zu "LPWSTR"|
|Compilerwarnung (Stufe 1) C4910|"\<Bezeichner >:"__declspec(dllexport)"und"Extern"sind bei einer expliziten Instanziierung nicht kompatibel|
|Compilerwarnung (Stufe 1) C4912|'Attribut': Das Attribut besitzt ein nicht definiertes Verhalten für ein geschachteltes UDT.|
|Compilerwarnung (Stufe 4) C4913|Benutzerdefinierter binärer Operator "," ist vorhanden, die Überladung konnte aber alle Operanden nicht konvertieren. Es wurde der standardmäßig enthaltene binäre Operator "," verwendet.|
|Compilerwarnung (Stufe 1) C4916|Um einen Dispid haben "*Beschreibung*': eine Schnittstelle eingeführt werden müssen|
|[Compilerwarnung (Ebene 1) C4917](compiler-warning-level-1-c4917.md)|'Deklarator': eine GUID kann nur eine Klasse, Schnittstelle oder ein Namespace zugeordnet werden|
|Compilerwarnung (Stufe 4) C4918|'Zeichen': Ungültiges Zeichen in der Pragma-Optimierungsliste|
|Compilerwarnung (Stufe 1) C4920|Enum Enum Member member_1 = value_1, die bereits in der Enum-enumerarion als member_2 = value_2|
|Compilerwarnung (Stufe 3) C4921|"*Beschreibung*":-Attributwert "*Attribut*" sollte nicht mehrfach angegeben werden|
|Compilerwarnung (Stufe 1) C4925|„method“: Die dispinterface-Methode kann nicht von einem Skript aufgerufen werden.|
|Compilerwarnung (Stufe 1) C4926|"Bezeichner": Symbol ist bereits definiert: Attribute werden ignoriert|
|[Compilerwarnung (Ebene 1) C4927](compiler-warning-level-1-c4927.md)|Unzulässige Konvertierung. mehrere benutzerdefinierte Konvertierungen wurden implizit übernommen.|
|[Compilerwarnung (Ebene 1) C4928](compiler-warning-level-1-c4928.md)|Unzulässige Kopierinitialisierung. Mehrere benutzerdefinierte Konvertierungen wurden implizit übernommen|
|[Compilerwarnung (Ebene 1) C4929](compiler-warning-level-1-c4929.md)|"File": Typbibliothek enthält eine Union. den Qualifizierer 'Embedded_idl' ignorieren|
|[Compilerwarnung (Ebene 1) C4930](compiler-warning-level-1-c4930.md)|'Prototyp': Funktion mit Prototyp nicht aufgerufen (war eine Variablendefinition vorgesehen?)|
|[Compilerwarnung (Ebene 4) C4931](compiler-warning-level-4-c4931.md)|Es wird angenommen, dass die Typbibliothek für Anzahl-Bit-Pointer erstellt wurde|
|Compilerwarnung (Stufe 4) C4932|__identifier (*Bezeichner*) und \__identifier (*Bezeichner*) sind nicht differenzierbar.|
|Compilerwarnung (Stufe 1) C4934|"__delegate(multicast)" ist veraltet, verwenden Sie "\__delegate" stattdessen|
|Compilerwarnung (Stufe 1) C4935|Assembly-Zugriffsspezifizierer wurde von "Zugriff" geändert.|
|Compilerwarnung (Stufe 1, Fehler) C4936|__declspec wird nur bei einer Kompilierung mit /clr oder /clr:pure unterstützt.|
|Compilerwarnung (Stufe 4) C4937|'Text1' und 'Text2' sind als Argumente für 'Direktive' nicht differenzierbar.|
|Compilerwarnung (Stufe 4) C4938|"Var": Reduction-Gleitkommavariable kann dazu führen, dass inkonsistente Ergebnissen bei/fp: strict oder #pragma fenv_access führen|
|Compilerwarnung C4939|#pragma vtordisp ist veraltet und wird in einem der nächsten Releases von Visual C++ entfernt.|
|Compilerwarnung (Stufe 1) C4944|'Symbol': Symbol aus 'assembly1' kann nicht importiert werden: 'Symbol' ist bereits im aktuellen Bereich vorhanden|
|[Compilerwarnung (Ebene 1) C4945](compiler-warning-level-1-c4945.md)|'Symbol': Symbol aus 'assembly1' kann nicht importiert werden: 'Symbol' wurde bereits von einer anderen Assembly "assembly2" importiert|
|[Compilerwarnung (Ebene 1) C4946](compiler-warning-level-1-c4946.md)|reinterpret_cast wird zwischen verknüpften Klassen verwendet: 'Klasse1' und 'Klasse2'|
|Compilerwarnung (Stufe 1) C4947|"Type_or_member": als veraltet markiert|
|[Compilerwarnung (Ebene 2) C4948](compiler-warning-level-2-c4948.md)|der Rückgabetyp von 'Accessor' entspricht nicht den letzten Parametertyp der entsprechenden Setter-Methode|
|[Compilerwarnung (Ebene 1 und Ebene 4) C4949](compiler-warning-level-1-and-level-4-c4949.md)|Pragmas "managed" und "nicht verwaltet" sind sinnvoll, nur beim Kompilieren mit "/ Clr [: Option]"|
|Compilerwarnung (Stufe 1, Fehler) C4950|"Type_or_member": als veraltet markiert|
|Compilerwarnung (Stufe 1) C4951|"Funktion" wurde bearbeitet, seit die Profildaten erfasst wurden. Die Funktionsprofildaten werden nicht verwendet.|
|Compilerwarnung (Stufe 1) C4952|'Funktion': keine Profildaten in der Programmdatenbank 'Pgd_file' gefunden|
|Compilerwarnung (Stufe 1) C4953|Inlinee "function" wurde bearbeitet, seit die Konfigurationsdaten erfasst wurden. Die Profildaten werden nicht verwendet|
|Compilerwarnung C4954|'Funktion': ein Profil nicht erstellt (__int64 Schalterausdruck enthält)|
|Compilerwarnung C4955|"import2": Import ignoriert. bereits importiert aus "import1".|
|Compilerwarnung (Stufe 1, Fehler) C4956|'Typ': Dieser Typ ist nicht überprüfbar|
|Compilerwarnung (Stufe 1, Fehler) C4957|"Umwandlung": explizite Umwandlung von 'Umwandlung von' in 'Cast_to' ist nicht überprüfbar|
|Compilerwarnung (Stufe 1, Fehler) C4958 generiert|'Operation': Zeigerarithmetik ist nicht überprüfbar|
|Compilerwarnung (Stufe 1, Fehler) C4959|nicht verwalteten Typ 'Typ' kann nicht in/CLR: safe definiert werden, da nicht überprüfbaren Code den Zugriff auf ihre Member ausgegeben wird.|
|Compilerwarnung (Stufe 4) C4960|"function" ist zu groß, um ein Profil zu erstellen|
|Compilerwarnung (Stufe 1) C4961|In 'PGD-Datei' wurden keine Profildaten zusammengeführt, profilgesteuerte Optimierungen werden deaktiviert.|
|Compilerwarnung (Stufe 4) C4962|'Funktion': Profilgesteuerte Optimierungen wurden deaktiviert, da Optimierungen Profildaten Profildaten verursacht hat.|
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
|[Compilerwarnung (Ebene 3) C4995](compiler-warning-level-3-c4995.md)|'Funktion': Name wurde als veraltet #pragma markiert|
|[Compilerwarnung (Ebene 3) C4996](compiler-warning-level-3-c4996.md)|"*Beschreibung*": *Nachricht*|
|Compilerwarnung (Stufe 1) C4997|„class“: Die Co-Klasse implementiert keine COM- oder Pseudoschnittstelle.|
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
