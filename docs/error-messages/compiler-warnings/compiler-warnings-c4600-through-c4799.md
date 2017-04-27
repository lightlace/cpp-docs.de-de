---
title: "Compilerfehler Warnungen C4600 über C4799 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- C4688
- C4689
- C4690
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
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 4bac7b2942f9d72674b8092dc7bf64174dd3c349
ms.openlocfilehash: 93c5e1f5d6e4615ca9cb022bf301bd73613ca31c
ms.lasthandoff: 04/24/2017

---
# <a name="compiler-warnings-c4600-through-c4799"></a>Compilerfehler Warnungen C4600 über C4799
In die Artikeln in diesem Teil der Dokumentation enthalten Informationen über eine Teilmenge von Visual C++-Compiler-Warnungen. Sie können die Informationen hier aufrufen oder, im Ausgabefenster in Visual Studio, können Sie eine Fehlernummer auswählen und dann die F1-Taste drücken.  
  
> [!NOTE]
>  Nicht jeder [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] Fehler oder eine Warnung in MSDN dokumentiert ist. In vielen Fällen enthält die diagnosemeldung alle Informationen, die verfügbar ist. Wenn Sie der Meinung sind, dass eine Fehlermeldung einer zusätzlichen Erklärung bedarf, informieren Sie uns bitte. Verwenden Sie die Feedback-Formular auf dieser Seite, oder wechseln Sie auf der Menüleiste in Visual Studio und wählen Sie **Hilfe**, **Melden eines Fehlers**, oder Sie können einen Bericht Vorschlag oder Fehler senden, auf [Microsoft Connect](http://connect.microsoft.com/VisualStudio).  
  
Sie möglicherweise zusätzliche Unterstützung für Fehler und Warnungen für den öffentlichen Foren von MSDN. Die [Visual C++-Sprache](http://go.microsoft.com/fwlink/?LinkId=158195) Forum eignet sich für Fragen und Diskussionen zu den [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] -Sprachsyntax und -Compiler. Die [Visual C++ Allgemein](http://go.microsoft.com/fwlink/?LinkId=158194) Forum eignet sich für Fragen zum [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] , die in anderen Foren nicht diskutiert werden. Sie können auch Hilfe zu Fehlern und Warnungen finden, auf [Stack Overflow](http://stackoverflow.com/).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|Warnung|Meldung|  
|-------------|-------------|  
|[Compilerwarnung (Ebene 1) C4600](../../error-messages/compiler-warnings/compiler-warning-level-1-c4600.md)|#Pragma 'Makroname': erwartet eine gültige nicht leere Zeichenfolge|  
|Compilerwarnung (Stufe 1) C4602|#Pragma-Pop_macro: 'Makroname' kein vorherigen #pragma Push_macro für diesen Bezeichner|  
|Compilerwarnung (Stufe 1) C4603|"\<Bezeichner >': Makro ist nicht definiert oder die Definition wurde nach Verwendung des vorkompilierten Headers|  
|[Compilerwarnung (Ebene 1) C4606](../../error-messages/compiler-warnings/compiler-warning-level-1-c4606.md)|#Pragma-Warnung: "Warnungsnummer' ignoriert. Codeanalysewarnungen sind nicht mit Warnstufen verknüpft.|  
|[Compilerwarnung (Ebene 3) C4608](../../error-messages/compiler-warnings/compiler-warning-level-3-c4608.md)|"union_member" wurde bereits von einem anderen Union-Member in der Initialisierungsliste initialisiert, "union_member"|  
|Compilerwarnung (Stufe 3) C4609|"%$S" leitet sich von Standardschnittstelle "%$S" für Typ "%$S". Verwenden Sie eine andere Standardschnittstelle für "%$S", oder unterbrochen Sie die Basistypen zu abgeleiteten Beziehung.|  
|[Compilerwarnung (Ebene 4) C4610](../../error-messages/compiler-warnings/compiler-warning-level-4-c4610.md)|'Class'-Objekt kann nie instanziiert werden – benutzerdefinierter Konstruktor erforderlich|  
|[Compilerwarnung (Ebene 4) C4611](../../error-messages/compiler-warnings/compiler-warning-level-4-c4611.md)|Interaktion zwischen "Function" und die Zerstörung von C++ ist nicht portabel|  
|Compilerwarnung (Stufe 1) C4612|Fehler im Namen der Includedatei|  
|Compilerwarnung (Stufe 1) C4613|"%$S": Klasse des Segments kann nicht geändert werden|  
|[Compilerwarnung (Ebene 1) C4615](../../error-messages/compiler-warnings/compiler-warning-level-1-c4615.md)|#Pragma-Warnung: Unbekannte Warnung Benutzertyp|  
|[Compilerwarnung (Ebene 1) C4616](../../error-messages/compiler-warnings/compiler-warning-level-1-c4616.md)|#Pragma-Warning: Warnungsnummer 'number' keine gültige compilerwarnung|  
|[Compilerwarnung (Ebene 1) C4618](../../error-messages/compiler-warnings/compiler-warning-level-1-c4618.md)|Pragma-Parameter enthalten eine leere Zeichenfolge; Pragma wird ignoriert|  
|[Compilerwarnung (Ebene 3) C4619](../../error-messages/compiler-warnings/compiler-warning-level-3-c4619.md)|#Pragma-Warnung: Keine Warnungsnummer 'Number' vorhanden ist|  
|Compilerwarnung (Stufe 1) C4620|Keine Postfix-Form von 'Operator ++' für den Typ 'Typ' gefunden, Präfix-Form verwendet|  
|[Compilerwarnung (Ebene 1) C4621](../../error-messages/compiler-warnings/compiler-warning-level-1-c4621.md)|keine Postfix-Form des Operators'--' für Typ "Type", Präfix-Form gefunden|  
|Compilerwarnung (Stufe 3) C4622|Überschreiben der Debuginformationen beim Anlegen der vorkompilierten Headerdatei in der Objektdatei angelegt wurden: "File"|  
|[Compilerwarnung (Ebene 4) C4623](../../error-messages/compiler-warnings/compiler-warning-level-4-c4623.md)|'abgeleitete Klasse': Standardkonstruktor wurde implizit als gelöscht definiert, da ein Basisklasse-Standardkonstruktor nicht zugegriffen werden kann oder gelöscht wurde|  
|[Compilerwarnung (Ebene 1) C4624](../../error-messages/compiler-warnings/compiler-warning-level-1-c4624.md)|'abgeleitete Klasse': Destruktor wurde implizit als gelöscht definiert, da ein Basisklassen-Destruktor nicht zugreifbar ist oder gelöscht wird|  
|[Compilerwarnung (Ebene 4) C4625](../../error-messages/compiler-warnings/compiler-warning-level-4-c4625.md)|'abgeleitete Klasse': Kopierkonstruktor wurde implizit als gelöscht definiert, da ein Basisklasse-Kopierkonstruktor nicht zugegriffen werden kann oder gelöscht wurde|  
|[Compilerwarnung (Ebene 4) C4626](../../error-messages/compiler-warnings/compiler-warning-level-4-c4626.md)|'abgeleitete Klasse': Zuweisungsoperator wurde implizit als gelöscht definiert, da ein Basisklasse-Zuweisungsoperator nicht zugegriffen werden kann oder gelöscht wurde|  
|[Compilerwarnung (Ebene 1) C4627](../../error-messages/compiler-warnings/compiler-warning-level-1-c4627.md)|"\<Bezeichner >": bei der Suche nach Verwendung des vorkompilierten Headers übersprungen|  
|[Compilerwarnung (Ebene 1) C4628](../../error-messages/compiler-warnings/compiler-warning-level-1-c4628.md)|'digraphs' werden mit '-Ze' nicht unterstützt. Die Zeichensequenz 'Digraph' wird nicht als alternativer Token für "%s" interpretiert.|  
|Compilerwarnung (Stufe 4) C4629|"Digraph" wurde verwendet, Zeichensequenz "Digraph" wurde als Token "Zeichen" interpretiert (Fügen Sie zwischen den beiden Zeichen ein Leerzeichen ein, wenn Sie etwas anderes beabsichtigt haben)|  
|[Compilerwarnung (Ebene 1) C4630](../../error-messages/compiler-warnings/compiler-warning-level-1-c4630.md)|'Symbol': Speicherklassenspezifizierer "Extern" für die Elementdefinition nicht zulässig|  
|Compilerwarnung (Stufe 2) C4631|MSXML oder XPath ist nicht verfügbar. XML-Dokumentkommentare werden nicht verarbeitet. reason|  
|[Compilerwarnung (Ebene 1) C4632](../../error-messages/compiler-warnings/compiler-warning-level-1-c4632.md)|XML-Dokumentkommentar: Datei - Zugriff verweigert: Grund|  
|[Compilerwarnung (Ebene 3) C4633](../../error-messages/compiler-warnings/compiler-warning-level-3-c4633.md)|XML-dokumentkommentarziel: Fehler: Grund|  
|Compilerwarnung (Stufe 4) C4634 generiert|XML-dokumentkommentarziel: kann nicht angewendet werden: Grund|  
|Compilerwarnung (Stufe 3) C4635|XML-Dokumentkommentarziel: Ungültige XML: Grund|  
|Compilerwarnung (Stufe 3) C4636|Angewendet, die zum Erstellen von XML-Dokumentkommentar: Tag erfordert nicht leeren ' Attribut '.|  
|Compilerwarnung (Stufe 3 und Ebene 4) C4637|XML-dokumentkommentarziel: \<enthalten >-Tag wurde verworfen. Grund|  
|Compilerwarnung (Stufe 3) C4638|XML-dokumentkommentarziel: Verweis auf unbekanntes Symbol 'Symbol'.|  
|[Compilerwarnung (Ebene 4) C4639](../../error-messages/compiler-warnings/compiler-warning-level-4-c4639.md)|MSXML Fehler, XML-Dokumentkommentare werden nicht verarbeitet. Grund|  
|[Compilerwarnung (Ebene 3) C4640](../../error-messages/compiler-warnings/compiler-warning-level-3-c4640.md)|„Instanz“: Erstellen eines lokalen static-Objekts ist nicht threadsicher|  
|[Compilerwarnung (Ebene 3) C4641](../../error-messages/compiler-warnings/compiler-warning-level-3-c4641.md)|Der XML-Dokumentkommentar enthält einen mehrdeutigen Querverweis:|  
|Compilerwarnung (Stufe 3) C4645|Eine Funktion, die mit "__declspec(noreturn)" deklariert wurde, hat eine Rückgabeanweisung|  
|Compilerwarnung (Stufe 3) C4646|Eine Funktion, die mit "__declspec(noreturn)" deklariert wurde, hat einen nicht leeren Rückgabetyp|  
|[Compilerwarnung (Ebene 1) C4650](../../error-messages/compiler-warnings/compiler-warning-level-1-c4650.md)|Debuginformationen nicht in vorkompilierter Headerdatei vorhanden; nur globale Symbole aus dieser Datei verfügbar|  
|[Compilerwarnung (Ebene 1) C4651](../../error-messages/compiler-warnings/compiler-warning-level-1-c4651.md)|"Definition" nach dem vorkompilierten Header, aber nicht für die aktuelle Kompilierung angegeben|  
|[Compilerwarnung (Ebene 1) C4652](../../error-messages/compiler-warnings/compiler-warning-level-1-c4652.md)|die Compileroption 'Option' inkonsistent mit der vorkompilierten Headerdatei; aktuelle Befehlszeilenoption überschreibt, die in der vorkompilierten Headerdatei definiert|  
|[Compilerwarnung (Ebene 2) C4653](../../error-messages/compiler-warnings/compiler-warning-level-2-c4653.md)|die Compileroption 'Option' inkonsistent mit der vorkompilierten Headerdatei; aktuelle Befehlszeilenoption wird ignoriert|  
|Compilerwarnung (Stufe 1) C4655|'Symbol': Variablentyp ist seit dem letzten Build neu, oder an anderer Stelle unterschiedlich definiert ist|  
|[Compilerwarnung (Ebene 1) C4656](../../error-messages/compiler-warnings/compiler-warning-level-1-c4656.md)|'Symbol': Datentyp Neuigkeiten gibt es seit dem letzten Build geändert hat oder an anderer Stelle unterschiedlich definiert ist|  
|Compilerwarnung (Stufe 1) C4657|Der Ausdruck bezieht einen Datentyp ein, der seit dem letzten Build neu hinzugekommen ist|  
|Compilerwarnung (Stufe 1) C4658|'Funktion': Funktionsprototyp ist seit dem letzten Build neu, oder an anderer Stelle unterschiedlich deklariert ist|  
|[Compilerwarnung (Ebene 1) C4659](../../error-messages/compiler-warnings/compiler-warning-level-1-c4659.md)|#Pragma 'Pragma': Verwendung von reservierten Segments "Segment" weist ein nicht definiertes Verhalten, verwenden Sie die #pragma-Kommentar (Linker,...)|  
|[Compilerwarnung (Ebene 1) C4661](../../error-messages/compiler-warnings/compiler-warning-level-1-c4661.md)|'Bezeichner': keine geeignete Definition für explizite Instanziierung Anforderung|  
|Compilerwarnung (Stufe 1) C4662|Explizite Instanziierung; Vorlagenklasse "Bezeichner1" besitzt keine Definition, von der "Bezeichner2" spezialisiert werden kann.|  
|[Compilerwarnung (Ebene 1) C4667](../../error-messages/compiler-warnings/compiler-warning-level-1-c4667.md)|'Funktion': keine Funktionsvorlage definiert, die entspricht erforderlichen Instanziierung|  
|[Compilerwarnung (Ebene 4) C4668](../../error-messages/compiler-warnings/compiler-warning-level-4-c4668.md)|'Symbol' ist als ein Präprozessormakro, ersetzen durch '0' für 'Direktive' nicht definiert.|  
|[Compilerwarnung (Ebene 1) C4669](../../error-messages/compiler-warnings/compiler-warning-level-1-c4669.md)|'cast': unsichere Konvertierung: "Klasse" ist ein verwalteter Typ-Objekt|  
|Compilerwarnung (Stufe 4) C4670|'Bezeichner': Diese Basisklasse ist nicht möglich|  
|Compilerwarnung (Stufe 4) C4671|'Bezeichner': der Kopierkonstruktor ist nicht möglich|  
|Compilerwarnung (Stufe 4) C4672|'Bezeichner1': mehrdeutig. Zuerst als 'identifier2' aufgetreten|  
|[Compilerwarnung (Ebene 4) C4673](../../error-messages/compiler-warnings/compiler-warning-level-4-c4673.md)|Auslösen von 'Bezeichner' die folgenden Typen werden nicht am Standort Catch angesehen|  
|Compilerwarnung (Stufe 1) c4674 generiert|"Methode" sollte als "static" deklariert werden und nur einen Parameter haben|  
|Compilerwarnung (Stufe 4) C4676|"%s": Auf den Destruktor kann nicht zugegriffen werden.|  
|[Compilerwarnung (Ebene 1) C4677](../../error-messages/compiler-warnings/compiler-warning-level-1-c4677.md)|'Funktion': Signatur des nicht privaten Members enthält den privaten Assemblytyp 'Private_type'|  
|Compilerwarnung (Stufe 1) C4678|Die Basisklasse 'base_type' hat eine stärkere Zugriffsbeschränkung als 'derived_type'|  
|[Compilerwarnung (Ebene 1) C4679](../../error-messages/compiler-warnings/compiler-warning-level-1-c4679.md)|"Member": Schnittstellenmember konnte nicht importiert|  
|[Compilerwarnung (Ebene 4) C4680](../../error-messages/compiler-warnings/compiler-warning-level-4-c4680.md)|'Klasse': Co-Klasse gibt keine Standardschnittstelle|  
|Compilerwarnung (Stufe 4) C4681|'Klasse': Co-Klasse gibt eine Standardschnittstelle an, die eine Ereignisquelle ist keine|  
|Compilerwarnung (Stufe 4) C4682|'Parameter': kein direktionales Parameterattribut angegeben, Standardwert [in]|  
|[Compilerwarnung (Ebene 1) C4683](../../error-messages/compiler-warnings/compiler-warning-level-1-c4683.md)|'Funktion': Ereignisquelle hat einen 'Out'-Parameter. Seien Sie vorsichtig, wenn mehrere Ereignishandler einbinden|  
|[Compilerwarnung (Ebene 1) C4684](../../error-messages/compiler-warnings/compiler-warning-level-1-c4684.md)|'Attribut': Warnung!! Attribut kann dazu führen, dass ungültige codegenerierung: mit Vorsicht verwenden|  
|Compilerwarnung (Stufe 1) C4685|"> >" erwartet. ">>" wurde beim Verarbeiten der Vorlagenparameter gefunden|  
|[Compilerwarnung (Ebene 3) C4686](../../error-messages/compiler-warnings/compiler-warning-level-3-c4686.md)|„benutzerdefinierter Typ“: mögliche Verhaltensänderung, Änderung in der UDT gibt Aufrufkonvention zurück|  
|[Compilerwarnung C4687](../../error-messages/compiler-warnings/compiler-warning-c4687.md)|'Klasse': eine versiegelte abstrakte Klasse kann nicht implementiert eine Schnittstelle "Schnittstelle"|  
|Compilerwarnung (Stufe 1) C4688|"constraint": Die Einschränkungsliste enthält den privaten Assemblytyp "type".|  
|Compilerwarnung (Stufe 1) C4689|"%c": Nicht unterstütztes Zeichen in "#pragma detect_mismatch"; "#pragma" wird ignoriert.|  
|Compilerwarnung (Stufe 4) C4690|[Emitidl (Pop)]: mehr POP-als Push-Vorgänge|  
|[Compilerwarnung (Ebene 1) C4691](../../error-messages/compiler-warnings/compiler-warning-level-1-c4691.md)|'Typ': Typ verwiesen wurde in nicht referenzierte Assembly "File", in der aktuellen Übersetzungseinheit verwendet stattdessen definierten Typ erwartet|  
|[Compilerwarnung (Ebene 1) C4692](../../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md)|'Funktion': Die Signatur des nicht privaten Members enthält den privaten systemeigenen Assemblytyp 'systemeigener_Typ'|  
|Compilerwarnung (Stufe 1) C4693|'Klasse': eine versiegelte abstrakte Klasse kann nicht einer beliebigen Instanz Instanz Member 'Member' aufweisen|  
|Compilerwarnung (Stufe 1) C4694|'Klasse': eine versiegelte abstrakte Klasse kann nicht Basisklasse 'basis_klasse' aufweisen|  
|Compilerwarnung (Stufe 1) C4695|#Pragma-Execution_character_set: "Zeichensatz" ist kein unterstützter Argument: derzeit wird nur "UTF-8" wird unterstützt.|  
|Compilerwarnung (Stufe 1) C4696|/ ZBvalue1 Option außerhalb des gültigen Bereichs. Annahme, dass 'Wert2'|  
|[Compilerwarnung (Ebene 1 und Ebene 4) C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md)|nicht initialisierten lokalen Variablen 'Name' verwendet|  
|[Compilerwarnung (Ebene 4) C4701](../../error-messages/compiler-warnings/compiler-warning-level-4-c4701.md)|möglicherweise nicht initialisierten lokalen Variablen 'Name' verwendet|  
|[Compilerwarnung (Ebene 4) C4702](../../error-messages/compiler-warnings/compiler-warning-level-4-c4702.md)|Unerreichbarer Code|  
|[Compilerwarnung (Ebene 4) C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)|Die möglicherweise nicht initialisierte lokale Zeigervariable "%s" wurde verwendet.|  
|[Compilerwarnung (Ebene 4) C4706](../../error-messages/compiler-warnings/compiler-warning-level-4-c4706.md)|Zuweisung in bedingtem Ausdruck|  
|[Compilerwarnung (Ebene 4) C4709](../../error-messages/compiler-warnings/compiler-warning-level-4-c4709.md)|Komma-Operator innerhalb eines Feldindex-Ausdrucks|  
|[Compilerwarnung (Ebene 4) C4710](../../error-messages/compiler-warnings/compiler-warning-level-4-c4710.md)|'Funktion': Funktion ist nicht inline|  
|[Compilerwarnung (Ebene 1) C4711](../../error-messages/compiler-warnings/compiler-warning-level-1-c4711.md)|' Funktion ' für die automatische Inlineerweiterung ausgewählt|  
|[Compilerwarnung (Ebene 4) C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md)|'Funktion' als __forceinline markiert nicht inline|  
|[Compilerwarnung (Ebene 1) C4715](../../error-messages/compiler-warnings/compiler-warning-level-1-c4715.md)|'Funktion': nicht alle Steuerelementpfade geben einen Wert zurück.|  
|[Compilerwarnung (Ebene 1) C4716](../../error-messages/compiler-warnings/compiler-warning-level-1-c4716.md)|'Funktion': muss einen Wert zurückgeben|  
|[Compilerwarnung (Ebene 1) C4717](../../error-messages/compiler-warnings/compiler-warning-level-1-c4717.md)|'Funktion': rekursiv für alle Steuerelementpfade Funktion führt dazu, dass Laufzeit Stapelüberlauf|  
|Compilerwarnung (Stufe 4) C4718|'Funktionsaufruf': rekursiver Aufruf besitzt keine Nebeneffekte, wird gelöscht|  
|Compilerwarnung (Stufe 1) C4719|Beim Angeben von Ofast, wurde eine doppelte Konstante gefunden. Verwenden Sie "f" als Suffix für eine einzelne Präzision|  
|Compilerwarnung (Stufe 2) C4720|Inline-Assembler-Berichte: "Meldung"|  
|Compilerwarnung (Stufe 1) C4721|'Funktion': nicht als systeminterne Funktion verfügbar|  
|Compilerwarnung (Stufe 1) C4722|'Funktion': Destruktor gibt nie Werte zurück, mögliche Speicherverluste|  
|[Compilerwarnung (Ebene 3) C4723](../../error-messages/compiler-warnings/compiler-warning-level-3-c4723.md)|Mögliche Division durch 0 (Null)|  
|Compilerwarnung (Stufe 3) C4724|Mögliches Modulo durch 0 (Null)|  
|Compilerwarnung (Stufe 3) C4725|Anweisung kann auf einigen Pentium-Prozessoren ungenau sein|  
|[Compilerwarnung (Ebene 1) C4727](../../error-messages/compiler-warnings/compiler-warning-level-1-c4727.md)|PCH namens vorkompilierter Header mit dem gleichen Zeitstempel in Datei1 "und" Datei2 gefunden wurde.  Verwenden erste PCH an.|  
|Compilerwarnung (Stufe 1) C4728|/Yl-Option wird ignoriert, da ein PCH-Verweis erforderlich ist.|  
|Compilerwarnung (Stufe 4) C4729|Die Funktion ist zu groß für auf Verlaufdiagrammen basierende Warnungen.|  
|[Compilerwarnung (Stufe 1) C4730](../../error-messages/compiler-warnings/compiler-warning-level-1-c4730.md)compilerwarnung (Stufe 1) C4730|'main': Kombinieren von _m64 und Ausdrücke möglicherweise falsche Code führen|  
|[Compilerwarnung (Ebene 1) C4731](../../error-messages/compiler-warnings/compiler-warning-level-1-c4731.md)|"Zeiger": Framezeigerregister "registrieren" von Inline-Assemblycode geändert|  
|Compilerwarnung (Stufe 1) C4732|"%s" (systemintern) wird von dieser Architektur nicht unterstützt.|  
|[Compilerwarnung (Ebene 1) C4733](../../error-messages/compiler-warnings/compiler-warning-level-1-c4733.md)|Inline-ASM weist "FS:0" zu: Der Handler ist nicht als sicherer Handler registriert.|  
|[Compilerwarnung (Ebene 3) C4738](../../error-messages/compiler-warnings/compiler-warning-level-3-c4738.md)|Das 32-Bit-Gleitkommaergebnis wird im Speicher gespeichert. Möglicherweise kommt es zu einem Leistungsverlust|  
|Compilerwarnung (Stufe 1) C4739|Für den Verweis auf die Variable 'var' ist nicht genügend Speicherplatz vorhanden.|  
|[Compilerwarnung (Ebene 4) C4740](../../error-messages/compiler-warnings/compiler-warning-level-4-c4740.md)|Durch das Fließen in den Inline-ASM-Code bzw. aus diesem heraus wird eine globale Optimierung unterdrückt.|  
|[Compilerwarnung (Ebene 1) C4742](../../error-messages/compiler-warnings/compiler-warning-level-1-c4742.md)|"Var" verfügt über andere Ausrichtung in "Datei1" und "Datei2": Anzahl und|  
|[Compilerwarnung (Ebene 1) C4743](../../error-messages/compiler-warnings/compiler-warning-level-1-c4743.md)|'Typ' hat eine unterschiedliche Größe in "Datei1" und "Datei2": Anzahl und die Anzahl der Bytes|  
|[Compilerwarnung (Ebene 1) C4744](../../error-messages/compiler-warnings/compiler-warning-level-1-c4744.md)|"Var" hat einen anderen Typ in "Datei1" und "Datei2": "Typ1" und "Typ2"|  
|[Compilerwarnung C4746](../../error-messages/compiler-warnings/compiler-warning-c4746.md)|flüchtige Zugriff von "%s" unterliegt/volatile des:\<Iso &#124; ms > festlegen; in Betracht __iso_volatile_load/Store systeminterne Funktionen|  
|[Compilerwarnung (Ebene 1) C4747](../../error-messages/compiler-warnings/compiler-warning-level-1-c4747.md)|Aufrufen von verwalteten 'Einstiegspunkt': verwalteter Code kann nicht ausgeführt werden, unter der Loadersperre, einschließlich des DLL-Einstiegspunkts und aufrufen, die aus der DLL-Einstiegspunkt wurde erreicht|  
|Compilerwarnung (Stufe 1) C4750|'Bezeichner': Funktion mit „_alloca()“ „inline“ in einer Schleife|  
|Compilerwarnung (Stufe 4) C4751|/arch:AVX gilt nicht für die Intel(R) Streaming SIMD Extensions, die sich in der Inline-ASM befinden.|  
|Compilerwarnung (Stufe 4) C4752|Es wurden Intel(R) Advanced Vector Extensions gefunden. Verwenden Sie /arch:AVX.|  
|Compilerwarnung (Stufe 4) C4754|Konvertierungsregeln für arithmetische Operationen im Vergleich zur %s(%d) bedeuten, dass ein Branch nicht ausgeführt werden kann. "%S" in "%s" (oder ähnlichen Typ von %d Bytes) umgewandelt.|  
|Compilerwarnung C4755|Konvertierungsregeln für arithmetische Operationen im Vergleich zur %s(%d) kann eine Verzweigung in einer Inline-Funktion kann nicht ausgeführt werden. "%S" in "%s" (oder ähnlichen Typ von %d Bytes) umgewandelt.|  
|[Compilerwarnung (Ebene 2) C4756](../../error-messages/compiler-warnings/compiler-warning-level-2-c4756.md)|Überlauf bei arithmetischer Auswertung einer Konstanten|  
|Compilerwarnung (Stufe 4) C4757|Das Subskript besteht aus einem großen unsignierten Wert. Wollten Sie eine negative Konstante erzielen?|  
|Compilerwarnung (Stufe 4) C4764|Die Ausrichtung von catch-Objekten kann nicht mehr als 16 Bytes betragen.|  
|Compilerwarnung (Stufe 4) C4767|Abschnittsname "%s" ist länger als acht Zeichen und wird vom Linker abgeschnitten|  
|Compilerwarnung C4770|Teilweise validierte Enumeration "%s" wird als Index verwendet|  
|[Compilerwarnung (Ebene 1) C4772](../../error-messages/compiler-warnings/compiler-warning-level-1-c4772.md)|#Import auf einen Typ aus einer fehlenden Typbibliothek verwiesen wird; 'fehlender_Typ' als Platzhalter verwendet|  
|[Compilerwarnung (Ebene 1) C4788](../../error-messages/compiler-warnings/compiler-warning-level-1-c4788.md)|'Bezeichner': Bezeichner wurde auf 'Anzahl' Zeichen gekürzt|  
|[Compilerwarnung (Ebene 1) C4789](../../error-messages/compiler-warnings/compiler-warning-level-1-c4789.md)|Der Puffer 'Bezeichner' mit der Größe von N-Bytes wird überlaufen; M-Bytes werden ab Offset L geschrieben.|  
|Compilerwarnung (Stufe 2) C4792|Die Funktion "%s" wurde unter Verwendung von sysimport und durch Verweis von systemeigenem Code deklariert. Eine Importbibliothek ist zum Verknüpfen erforderlich|  
|[Compilerwarnung (Ebene 1 und 3) C4793](../../error-messages/compiler-warnings/compiler-warning-level-1-and-3-c4793.md)|"Funktion': Funktion, die als systemeigene: \n\t'reason kompiliert"|  
|Compilerwarnung (Stufe 1) C4794|Segment der Variable "%s" im lokalen Thread-Speicher von "%s" nach "%s" verschoben|  
|[Compilerwarnung (Ebene 1) C4799](../../error-messages/compiler-warnings/compiler-warning-level-1-c4799.md)|' Funktion ' hat keine EMMS-Anweisung|
