---
title: "Compilerfehler Warnungen C4800 über C4999 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4806
- C4807
- C4810
- C4811
- C4812
- C4813
- C4816
- C4817
- C4822
- C4825
- C4827
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
- C4808
- C4809
dev_langs:
- C++
ms.assetid: c3182430-8b3b-4ab2-a532-5cd436707dc8
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 4bac7b2942f9d72674b8092dc7bf64174dd3c349
ms.openlocfilehash: ac03a99c1a9413b697b6e40101bf1c3e2be9a3a6
ms.lasthandoff: 04/24/2017

---
# <a name="compiler-warnings-c4800-through-c4999"></a>Compilerfehler Warnungen C4800 über C4999
In die Artikeln in diesem Teil der Dokumentation enthalten Informationen über eine Teilmenge von Visual C++-Compiler-Warnungen. Sie können die Informationen hier aufrufen oder, im Ausgabefenster in Visual Studio, können Sie eine Fehlernummer auswählen und dann die F1-Taste drücken.  
  
> [!NOTE]
>  Nicht jeder [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] Fehler oder eine Warnung in MSDN dokumentiert ist. In vielen Fällen enthält die diagnosemeldung alle Informationen, die verfügbar ist. Wenn Sie der Meinung sind, dass eine Fehlermeldung einer zusätzlichen Erklärung bedarf, informieren Sie uns bitte. Verwenden Sie die Feedback-Formular auf dieser Seite, oder wechseln Sie auf der Menüleiste in Visual Studio und wählen Sie **Hilfe**, **Melden eines Fehlers**, oder Sie können einen Bericht Vorschlag oder Fehler senden, auf [Microsoft Connect](http://connect.microsoft.com/VisualStudio).  
  
Sie möglicherweise zusätzliche Unterstützung für Fehler und Warnungen für den öffentlichen Foren von MSDN. Die [Visual C++-Sprache](http://go.microsoft.com/fwlink/?LinkId=158195) Forum eignet sich für Fragen und Diskussionen zu den [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] -Sprachsyntax und -Compiler. Die [Visual C++ Allgemein](http://go.microsoft.com/fwlink/?LinkId=158194) Forum eignet sich für Fragen zum [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] , die in anderen Foren nicht diskutiert werden. Sie können auch Hilfe zu Fehlern und Warnungen finden, auf [Stack Overflow](http://stackoverflow.com/).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|Warnung|Meldung|  
|-------------|-------------|  
|[Compilerwarnung (Ebene 3) C4800](../../error-messages/compiler-warnings/compiler-warning-level-3-c4800.md)|'Typ': erzwungen wird Wert Bool 'True' oder 'False' (Leistung Warnung)|  
|[Compilerwarnung (Ebene 1) C4803](../../error-messages/compiler-warnings/compiler-warning-level-1-c4803.md)|'Methode': Die Raise-Methode wurde eine anderen Speicherklasse aus, der das Ereignis 'Ereignis'|  
|[Compilerwarnung (Ebene 1) C4804](../../error-messages/compiler-warnings/compiler-warning-level-1-c4804.md)|'Operation': unsichere Verwendung des Typs "Bool", Vorgang|  
|[Compilerwarnung (Ebene 1) C4805](../../error-messages/compiler-warnings/compiler-warning-level-1-c4805.md)|'Operation': Unsichere Kombination von Typ 'Typ' mit Typ "Typ" in-Vorgang|  
|Compilerwarnung (Stufe 1) C4806|'Operation': unsichere Operation: kein Wert vom Typ "Typ" Typ "type" höher gestuft, kann der angegebenen Konstante übereinstimmen|  
|Compilerwarnung (Stufe 1) C4807|'Operation': Unsichere Kombination von Typ "Typ" und signiertem Bitfeld des Typs "Typ"|  
|Compilerwarnung (Stufe 1) C4808|Case 'Wert' ist kein gültiger Wert für Switch-Bedingung vom Typ "Bool"|  
|Compilerwarnung (Stufe 1) C4809|switch-Anweisungen enthält redundante "default"-Bezeichnung; alle möglichen "case"-Bezeichnungen sind bereits angegeben|  
|Compilerwarnung (Stufe 1) C4810|Wert von pragma pack(show) == n|  
|Compilerwarnung (Stufe 1) C4811|Wert von 'pragma conform(forScope, show) == Wert'|  
|Compilerwarnung (Stufe 1) C4812|Veralteter Deklarationsstil: Verwenden Sie stattdessen „new_syntax“.|  
|Compilerwarnung (Stufe 1) C4813|'Funktion': eine Friend-Funktion einer lokalen Klasse muss bereits deklariert|  
|Compilerwarnung (Stufe 4) C4816|'Param': Parameter hat ein Array der Größe 0 (null), das abgeschnitten wird (es sei denn, das Objekt als Verweis übergeben wird)|  
|Compilerwarnung (Stufe 1) C4817|'Member': Unzulässige Verwendung von "." auf diesen Member. Compilerfehler ersetzt durch "->"|  
|[Compilerwarnung (Ebene 1) C4819](../../error-messages/compiler-warnings/compiler-warning-level-1-c4819.md)|Die Datei enthält ein Zeichen, das in der aktuellen Codepage (Nummer) nicht dargestellt werden kann. Speichern Sie die Datei im Unicode-Format, um Datenverluste zu vermeiden|  
|[Compilerwarnung (Ebene 4) C4820](../../error-messages/compiler-warnings/compiler-warning-level-4-c4820.md)|'Bytes' Bytes Abstand nach dem Konstrukt 'member_name'|  
|[Compilerwarnung (Ebene 1) C4821](../../error-messages/compiler-warnings/compiler-warning-level-1-c4821.md)|Unicode-Codierungstyp konnte nicht bestimmt werden, speichern Sie die Datei mit Signatur (BOM).|  
|Compilerwarnung (Stufe 1) C4822|"Member Function": Lokale Klassenmemberfunktion keinen Text enthalten.|  
|[Compilerwarnung (Ebene 3) C4823](../../error-messages/compiler-warnings/compiler-warning-level-3-c4823.md)|'Funktion': verwendet, die feste Zeiger, aber entladen nicht aktiviert. Erwägen Sie/EHa|  
|Compilerwarnung (Stufe 4) C4825||  
|Compilerwarnung (Stufe 3) C4827|Eine öffentliche "ToString"-Methode mit 0 Parametern muss als "virtual" und "override" markiert werden.|  
|[Compilerwarnung (Ebene 1) C4829](../../error-messages/compiler-warnings/compiler-warning-level-1-c4829.md)|Möglicherweise falsche Parameter für Main-Funktion. Betrachten Sie ' Int main (Platform:: Array\<Platform:: String ^ > ^ Argv)'|  
|[Compilerwarnung (Ebene 1) C4835](../../error-messages/compiler-warnings/compiler-warning-level-1-c4835.md)|'Variable': die Initialisierung für die exportierten Daten wird nicht ausgeführt, bis verwalteter Code in der Hostassembly zuerst ausgeführt wird|  
|[Compilerwarnung (Ebene 1) C4838](../../error-messages/compiler-warnings/compiler-warning-level-1-c4838.md)|Konvertierung von 'type_1' zu 'type_2' ist eine einschränkende Konvertierung erforderlich.|  
|[Compilerwarnung C4867](../../error-messages/compiler-warnings/compiler-warning-c4867.md)|'Funktion': Funktionsaufruf fehlt die Argumentliste. Verwenden Sie "Aufruf" So erstellen einen Zeiger auf member|  
|[Compilerwarnung C4868](../../error-messages/compiler-warnings/compiler-warning-c4868.md)|"file(line_number)" Compiler möglicherweise die Reihenfolge der Auswertung von links nach rechts in der Initialisierungsliste nicht erzwungen.|  
|Compilerwarnung (Stufe 2) C4872|Beim Kompilieren des Aufrufdiagramms für "concurrency::parallel_for_each" bei "%s" wurde eine Gleitkommadivision durch Null festgestellt.|  
|Compilerwarnung (Stufe 1) C4880|Umwandlung von 'const type_1' zu 'type_2': Umwandlung von einem Zeiger oder Verweis Constness möglicherweise zu nicht definiertem Verhalten in einer eingeschränkten Amp-Funktion|  
|Compilerwarnung (Stufe 4) C4881|der Konstruktor und/oder des Destruktors wird nicht für "tile_static"-Variable 'Variable' aufgerufen werden|  
|Compilerwarnung (Stufe 1) C4882|Das Übergeben von functor-Objekten mit nicht konstanten Aufrufoperatoren an "concurrency::parallel_for_each" ist veraltet|  
|Compilerwarnung C4900|Konflikt zwischen "tool1" Version "version1" und "tool2" Version "version2"|  
|[Compilerwarnung (Ebene 1) C4905](../../error-messages/compiler-warnings/compiler-warning-level-1-c4905.md)|
          Breites Zeichenfolgenliteral umgewandelt zu "LPSTR"|  
|[Compilerwarnung (Ebene 1) C4906](../../error-messages/compiler-warnings/compiler-warning-level-1-c4906.md)|
          Zeichenfolgenliteral umgewandelt zu "LPWSTR"|  
|Compilerwarnung (Stufe 1) C4910|"\<Bezeichner >:"__declspec(dllexport)"und"Extern"sind bei einer expliziten Instanziierung nicht kompatibel|  
|Compilerwarnung (Stufe 1) C4912|'Attribut': Das Attribut besitzt ein nicht definiertes Verhalten für ein geschachteltes UDT.|  
|Compilerwarnung (Stufe 4) C4913|Benutzerdefinierter binärer Operator "," ist vorhanden, die Überladung konnte aber alle Operanden nicht konvertieren. Es wurde der standardmäßig enthaltene binäre Operator "," verwendet.|  
|Compilerwarnung (Stufe 1) C4916|"%$S" muss von einer Schnittstelle eingeführt werden, um eine "dispid" zu besitzen|  
|[Compilerwarnung (Ebene 1) C4917](../../error-messages/compiler-warnings/compiler-warning-level-1-c4917.md)|'Deklarator': eine GUID kann nur eine Klasse, Schnittstelle oder ein Namespace zugeordnet werden|  
|Compilerwarnung (Stufe 4) C4918|'Zeichen': Ungültiges Zeichen in der Pragma-Optimierungsliste|  
|Compilerwarnung (Stufe 1) C4920|Enum Enum Member member_1 = value_1, die bereits in der Enum-enumerarion als member_2 = value_2|  
|Compilerwarnung (Stufe 3) C4921|"%s": Der Attributwert "%s" sollte nicht mehrfach bestimmt werden|  
|Compilerwarnung (Stufe 1) C4925|„method“: Die dispinterface-Methode kann nicht von einem Skript aufgerufen werden.|  
|Compilerwarnung (Stufe 1) C4926|"Bezeichner": Symbol ist bereits definiert: Attribute werden ignoriert|  
|[Compilerwarnung (Ebene 1) C4927](../../error-messages/compiler-warnings/compiler-warning-level-1-c4927.md)|Unzulässige Konvertierung. Mehrere benutzerdefinierte Konvertierungen wurden implizit übernommen.|  
|[Compilerwarnung (Ebene 1) C4928](../../error-messages/compiler-warnings/compiler-warning-level-1-c4928.md)|Unzulässige Kopierinitialisierung. Mehrere benutzerdefinierte Konvertierungen wurden implizit übernommen|  
|[Compilerwarnung (Ebene 1) C4929](../../error-messages/compiler-warnings/compiler-warning-level-1-c4929.md)|"File": Typbibliothek enthält eine Union. den Qualifizierer 'Embedded_idl' ignorieren|  
|[Compilerwarnung (Ebene 1) C4930](../../error-messages/compiler-warnings/compiler-warning-level-1-c4930.md)|'Prototyp': Funktion mit Prototyp nicht aufgerufen (war eine Variablendefinition vorgesehen?)|  
|[Compilerwarnung (Ebene 4) C4931](../../error-messages/compiler-warnings/compiler-warning-level-4-c4931.md)|Es wird angenommen, dass die Typbibliothek für Anzahl-Bit-Pointer erstellt wurde|  
|Compilerwarnung (Stufe 4) C4932|__identifier(Bezeichner) und \__identifier(identifier) sind nicht differenzierbar.|  
|Compilerwarnung (Stufe 1) C4934|"__delegate(multicast)" ist veraltet, verwenden Sie "\__delegate" stattdessen|  
|Compilerwarnung (Stufe 1) C4935|Assembly-Zugriffsspezifizierer wurde von "Zugriff" geändert.|  
|Compilerwarnung (Stufe 1) C4936|__declspec wird nur bei einer Kompilierung mit /clr oder /clr:pure unterstützt.|  
|Compilerwarnung (Stufe 4) C4937|'Text1' und 'Text2' sind als Argumente für 'Direktive' nicht differenzierbar.|  
|Compilerwarnung (Stufe 4) C4938|"Var": Reduction-Gleitkommavariable kann dazu führen, dass inkonsistente Ergebnissen bei/fp: strict oder #pragma fenv_access führen|  
|Compilerwarnung C4939|#Pragma-Vtordisp ist veraltet und wird in einer zukünftigen Version von Visual C++ entfernt|  
|Compilerwarnung (Stufe 1) C4944|'Symbol': Symbol aus 'assembly1' kann nicht importiert werden: 'Symbol' ist bereits im aktuellen Bereich vorhanden|  
|[Compilerwarnung (Ebene 1) C4945](../../error-messages/compiler-warnings/compiler-warning-level-1-c4945.md)|'Symbol': Symbol aus 'assembly1' kann nicht importiert werden: 'Symbol' wurde bereits von einer anderen Assembly "assembly2" importiert|  
|[Compilerwarnung (Ebene 1) C4946](../../error-messages/compiler-warnings/compiler-warning-level-1-c4946.md)|reinterpret_cast wird zwischen verknüpften Klassen verwendet: 'Klasse1' und 'Klasse2'|  
|Compilerwarnung (Stufe 1) C4947|"Type_or_member": als veraltet markiert|  
|[Compilerwarnung (Ebene 2) C4948](../../error-messages/compiler-warnings/compiler-warning-level-2-c4948.md)|der Rückgabetyp von 'Accessor' entspricht nicht den letzten Parametertyp der entsprechenden Setter-Methode|  
|[Compilerwarnung (Ebene 1 und Ebene 4) C4949](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4949.md)|Pragmas "managed" und "nicht verwaltet" sind sinnvoll, nur beim Kompilieren mit "/ Clr [: Option]"|  
|Compilerwarnung (Stufe 1) C4950|"Type_or_member": als veraltet markiert|  
|Compilerwarnung C4951|"Funktion" wurde bearbeitet, seit die Profildaten erfasst wurden. Die Funktionsprofildaten werden nicht verwendet.|  
|Compilerwarnung C4952|'Funktion': keine Profildaten in der Programmdatenbank 'Pgd_file' gefunden|  
|Compilerwarnung C4953|Inline "Function" wurde bearbeitet, seit die Profildaten erfasst wurden, nicht verwendet Profildaten|  
|Compilerwarnung C4954|'Funktion': ein Profil nicht erstellt (__int64 Schalterausdruck enthält)|  
|Compilerwarnung C4955|"import2": Import ignoriert. bereits importiert aus "import1".|  
|Compilerwarnung (Stufe 1) C4956|'Typ': Dieser Typ ist nicht überprüfbar|  
|Compilerwarnung (Stufe 1) C4957|"Umwandlung": explizite Umwandlung von 'Umwandlung von' in 'Cast_to' ist nicht überprüfbar|  
|Compilerwarnung (Stufe 1) C4958 generiert|'Operation': Zeigerarithmetik ist nicht überprüfbar|  
|Compilerwarnung (Stufe 1) C4959|nicht verwalteten Typ 'Typ' kann nicht in/CLR: safe definiert werden, da nicht überprüfbaren Code den Zugriff auf ihre Member ausgegeben wird.|  
|Compilerwarnung C4960|"function" ist zu groß, um ein Profil zu erstellen|  
|Compilerwarnung C4961|In 'PGD-Datei' wurden keine Profildaten zusammengeführt, profilgesteuerte Optimierungen werden deaktiviert.|  
|Compilerwarnung C4962|'Funktion': Profilgesteuerte Optimierungen wurden deaktiviert, da Optimierungen Profildaten Profildaten verursacht hat.|  
|Compilerwarnung C4963|%s': keine Profildaten gefunden. verschiedene Compileroptionen wurden in den instrumentierten Build verwendet werden.|  
|[Compilerwarnung (Ebene 1) C4964](../../error-messages/compiler-warnings/compiler-warning-level-1-c4964.md)|Es wurden keine Optimierungsoptionen angegeben. Es werden keine Profilinformationen erfasst.|  
|[Compilerwarnung (Ebene 1) C4965](../../error-messages/compiler-warnings/compiler-warning-level-1-c4965.md)|Implizites Boxing mit ganzer Zahl 0. Verwenden Sie "nullptr" oder eine explizite Umwandlung.|  
|Compilerwarnung C4966|"%s" hat eine __code_seg-Anmerkung mit nicht unterstütztem Segmentnamen, Anmerkung wird ignoriert.|  
|Compilerwarnung C4970|Delegatkonstruktor: Das Zielobjekt wird ignoriert, da "%$pS" statisch ist.|  
|Compilerwarnung (Stufe 1) C4971|Argument Order: \<Zielobjekt >, \<Funktion als Ziel > für Delegatkonstruktor veraltet ist, verwenden Sie \<Ziel Funktion >, \<Zielobjekt = "" >|  
|Compilerwarnung (Stufe 1) C4972|Das direkte Ändern oder Behandeln des Ergebnisses eines Unboxing-Vorgangs als L-Wert kann nicht überprüft werden.|  
|Compilerwarnung C4973|"%$S" : als veraltet markiert|  
|Compilerwarnung C4974|"%$S" : als veraltet markiert|  
|Compilerwarnung C4981|Warbird: Die als __forceinline markierte "%$pD"-Funktion ist nicht "inline", da sie Ausnahmesemantik enthält.|  
|Compilerwarnung (Stufe 3) C4985|Symbolname ": Attribute in vorheriger Deklaration nicht vorhanden sind.|  
|[Compilerwarnung C4986](../../error-messages/compiler-warnings/compiler-warning-c4986.md)|"%$pS": Die Ausnahmespezifikation stimmt nicht mit der vorherigen Deklaration überein.|  
|Compilerwarnung (Stufe 4) C4987|Es wurde eine nicht standardmäßige Erweiterung verwendet: 'throw (...)'|  
|Compilerwarnung (Stufe 4) C4988|"%$S": Die Variable wurde außerhalb des Klassen-/Funktionsbereichs deklariert.|  
|Compilerwarnung C4989|"%s": Der Typ weist in Konflikt stehende Definitionen auf.|  
|Compilerwarnung C4990|Warbird: %s|  
|Compilerwarnung C4991|Warbird: Die als __forceinline markierte "%$pD"-Funktion ist nicht "inline", da die Schutzstufe des Inlinees größer als das übergeordnete Element ist.|  
|Compilerwarnung C4992|Warbird: Die als __forceinline markierte "%$pD"-Funktion ist nicht "inline", da sie eine Inlineassembly enthält, die nicht geschützt werden kann.|  
|[Compilerwarnung (Ebene 3) C4995](../../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)|'Funktion': Name wurde als veraltet #pragma markiert|  
|[Compilerwarnung (Ebene 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)|'%$pS': %$*|  
|Compilerwarnung (Stufe 1) C4997|„class“: Die Co-Klasse implementiert keine COM- oder Pseudoschnittstelle.|  
|Compilerwarnung (Stufe 1) C4998|ERWARTUNG FEHLGESCHLAGEN: %s(%d)|  
|Compilerwarnung C4999|UNBEKANNTE WARNUNG %$N Klicken Sie im Menü "Hilfe" von Visual C++ %$N auf "Technischer Support", oder öffnen Sie die Hilfedatei zum technischen Support, um weitere Informationen zu erhalten.|
