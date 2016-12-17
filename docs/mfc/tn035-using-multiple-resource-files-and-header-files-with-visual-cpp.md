---
title: "TN035: Verwenden mehrerer Ressourcendateien und Headerdateien mit Visual C++"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.resources"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ressourcendateien, mehrere"
  - "TN035"
ms.assetid: 1f08ce5e-a912-44cc-ac56-7dd93ad73fb6
caps.latest.revision: 13
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# TN035: Verwenden mehrerer Ressourcendateien und Headerdateien mit Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 In diesem Hinweis wird beschrieben, wie der Visual C\+\+\-Ressourcen\-Editor mehrere entweder in einem einzelnen Projekt oder in mehreren Projekten gemeinsam genutzte Ressourcendateien und Headerdateien unterstützt und wie Sie von dieser Unterstützung profitieren.  In dem Hinweis werden folgende Fragen beantwortet:  
  
-   In welchen Fällen sollten Sie ein Projekt in mehrere Ressourcendateien und\/oder Headerdateien aufteilen, und wie gehen Sie dabei vor?  
  
-   Wie kann eine allgemeine H\-Headerdatei für zwei RC\-Dateien freigegeben werden?  
  
-   Wie teilen Sie Projektressourcen in mehrere RC\-Dateien?  
  
-   Wie verwalten Sie \(und die Tools\) Buildabhängigkeiten zwischen RC\-, CPP\- und H\-Dateien?  
  
 Wenn Sie Ihrem Projekt eine zusätzliche Ressourcendatei hinzufügen, erkennt ClassWizard die Ressourcen in der hinzugefügten Datei nicht.  
  
 Die oben genannten Fragen werden in diesem Hinweis anhand der folgenden Gliederung beantwortet:  
  
-   **Overview of How Visual C\+\+ Manages Resource Files and Header Files** bietet eine Übersicht darüber, wie Sie mit dem Befehl "Gruppe enthält" für Ressourcen in Visual C\+\+ mehrere Ressourcendateien und Headerdateien im selben Projekt verwenden können.  
  
-   In **Analysis of AppWizard\-created .RC and .H Files** werden die verschiedenen Ressourcen\- und Headerdateien untersucht, die von einer von AppWizard erstellten Anwendung verwendet werden.  Diese Dateien sind ein gutes Beispiel für zusätzliche Ressourcen\- und Headerdateien, die Sie dem Projekt hinzufügen können.  
  
-   In **Including Additional Header Files** wird beschrieben, wo Sie mehrere Headerdateien hinzufügen können, und es wird detailliert erläutert, wie Sie dabei vorgehen.  
  
-   In **Sharing a Header File Between Two .RC Files** wird gezeigt, wie Sie eine einzelne Headerdatei für mehrere RC\-Dateien in verschiedenen Projekten oder auch im selben Projekt freigeben können.  
  
-   In **Using Multiple Resource Files in the Same Project** wird beschrieben, wie Sie das Projekt in mehrere RC\-Dateien aufteilen können, und es wird detailliert erläutert, wie Sie dabei vorgehen.  
  
-   In **Enforcement of Non\-Editable Visual C\+\+ Files** wird erläutert, wie Sie sicherstellen können, dass Visual C\+\+ eine benutzerdefinierte Ressource nicht bearbeitet und versehentlich umformatiert.  
  
-   In **Managing Symbols Shared by Multiple Visual C\+\+\-Edited .RC Files** wird beschrieben, wie Sie die gleichen Symbole für mehrere RC\-Dateien gemeinsam nutzen können und wie Sie verhindern, dass doppelte numerische ID\-Werte zugewiesen werden.  
  
-   In **Managing Dependencies Between .RC, .CPP, and .H Files** wird erläutert, wie Sie in Visual C\+\+ eine unnötige Neukompilierung von CPP\-Dateien vermeiden, die von Ressourcensymboldateien abhängig sind.  
  
-   **How Visual C\+\+ Manages Set Includes Information** bietet technische Details dazu, wie Visual C\+\+ mehrere \(geschachtelte\) RC\-Dateien und mehrere Headerdateien nachverfolgt, die durch eine RC\-Datei mit \#include eingebunden wurden.  
  
 **Übersicht über die Verwaltung von Ressourcendateien und Headerdateien in Visual C\+\+**  
  
 Visual C\+\+ verwaltet eine einzelne RC\-Ressourcendatei und eine entsprechende H\-Headerdatei als eng gekoppeltes Dateienpaar.  Wenn Sie Ressourcen in einer RC\-Datei bearbeiten und speichern, bearbeiten und speichern Sie indirekt Symbole in der entsprechenden H\-Datei.  Obwohl Sie \(über die MDI\-Benutzeroberfläche von Visual C\+\+\) mehrere RC\-Dateien gleichzeitig für eine RC\-Datei öffnen und bearbeiten können, bearbeiten Sie indirekt genau eine entsprechende Headerdatei.  
  
 **Symbolheaderdatei**  
  
 Standardmäßig wird der entsprechenden Headerdatei in Visual C\+\+ immer der Name RESOURCE.H zugewiesen, unabhängig vom Namen der Ressourcendatei \(z. B. MYAPP.RC\).  Mithilfe des Befehls **Ressourcenincludes** im Menü **Ansicht** in Visual C\+\+ können Sie den Namen dieser Headerdatei ändern, indem Sie die Datei "Symbolheaderdatei" im Dialogfeld **Gruppe enthält** aktualisieren.  
  
 **Direktiven für schreibgeschützte Symbole**  
  
 Obwohl in Visual C\+\+ nur jeweils eine Headerdatei für eine RC\-Datei bearbeitet werden kann, unterstützt Visual C\+\+ Verweise auf Symbole, die in zusätzlichen schreibgeschützten Headerdateien definiert sind.  Mithilfe des Befehls **Ressourcenincludes** im Menü **Ansicht** in Visual C\+\+ können Sie eine beliebige Anzahl zusätzlicher schreibgeschützter Headerdateien als Direktiven für schreibgeschützte Symbole angeben.  Die Einschränkung "schreibgeschützt" bedeutet, dass Sie beim Hinzufügen einer neuen Ressource in der RC\-Datei ein Symbol verwenden können, das in der schreibgeschützten Headerdatei definiert ist. Wenn Sie die Ressource löschen, bleibt das Symbol weiterhin in der schreibgeschützten Headerdatei definiert.  Sie können den numerischen Wert nicht ändern, der einem schreibgeschützten Symbol zugewiesen ist.  
  
 **Kompilierzeitdirektiven**  
  
 Visual C\+\+ unterstützt auch die Schachtelung von Ressourcendateien, bei der eine RC\-Datei mit \#include in eine andere eingebunden wird.  Wenn Sie eine bestimmte RC\-Datei mit Visual C\+\+ bearbeiten, sind die Ressourcen in den mit \#include eingebundenen Dateien nicht sichtbar.  Wenn Sie die RC\-Datei jedoch kompilieren, werden die mit \#include eingebundenen Dateien ebenfalls kompiliert.  Mithilfe des Befehls **Ressourcenincludes** im Menü **Ansicht** in Visual C\+\+ können Sie eine beliebige Anzahl von mit \#include eingebundenen RC\-Dateien als Kompilierzeitdirektiven angeben.  
  
 Beachten Sie, was geschieht, wenn Sie eine RC\-Datei in Visual C\+\+ einlesen, die mit \#include eine andere RC\-Datei einbindet, welche *nicht* als Kompilierzeitdirektive angegeben ist.  Dieser Fall kann eintreten, wenn Sie eine RC\-Datei in Visual C\+\+ übertragen, die Sie zuvor manuell mit einem Text\-Editor verwaltet haben.  Wenn Visual C\+\+ die mit \#include eingebundene RC\-Datei liest, werden die mit \#include eingebundenen Ressourcen in der übergeordneten RC\-Datei zusammengeführt.  Wenn Sie die übergeordnete RC\-Datei speichern, wird die \#include\-Anweisung durch die mit \#include eingebundenen Ressourcen ersetzt.  Wenn Sie diese Zusammenführung nicht wünschen, sollten Sie die \#include\-Anweisung *vor* dem Einlesen in Visual C\+\+ aus der übergeordneten RC\-Datei entfernen. Danach fügen Sie die \#include\-Anweisung mit Visual C\+\+ wieder als Kompilierzeitdirektive hinzu.  
  
 Visual C\+\+ speichert in einer RC\-Datei die drei Arten der oben genannten "Gruppe enthält"\-Informationen \(Symbolheaderdatei, schreibgeschützte Symboldirektiven und Kompilierzeitdirektiven\) in \#include\-Direktiven *und* in TEXTINCLUDE\-Ressourcen.  Die TEXTINCLUDE\-Ressourcen, ein Implementierungsdetail, um das Sie sich normalerweise nicht kümmern müssen, werden in [Verwaltung von "Gruppe enthält"\-Informationen in Visual C\+\+](#_mfcnotes_tn035_set_includes) erläutert.  
  
 **Analyse der von AppWizard erstellten RC\- und H\-Dateien**  
  
 Eine Überprüfung des von AppWizard erzeugten Anwendungscodes liefert Informationen darüber, wie in Visual C\+\+ mehrere Ressourcendateien und Headerdateien verwaltet werden.  Die nachfolgend untersuchten Codeauszüge stammen von einer MYAPP\-Anwendung, die von AppWizard unter Verwendung der Standardoptionen erstellt wurde.  
  
 Eine von AppWizard erstellte Anwendung verwendet mehrere Ressourcendateien und mehrere Headerdateien, wie im folgenden Diagramm dargestellt:  
  
```  
RESOURCE.H     AFXRES.H                      
       \       /                                
        \     /                                  
       MYAPP.RC                                 
           |                                  
           |                                
     RES\MYAPP.RC2    
     AFXRES.RC                     
     AFXPRINT.RC                   
```  
  
 Sie können diese Beziehungen zwischen mehreren Dateien mit dem Befehl "Visual C\+\+\-Datei\/Gruppe enthält" anzeigen.  
  
 MYAPP.RC  
 Die Anwendungsressourcendatei, die Sie mit Visual C\+\+ bearbeiten.  
  
 RESOURCE.H ist die anwendungsspezifische Headerdatei.  Sie erhält von AppWizard immer den Namen RESOURCE.H, entsprechend der Standardbenennung der Headerdatei in Visual C\+\+.  Die \#include\-Direktive für diese Headerdatei ist die erste Anweisung in der Ressourcendatei \(MYAPP.RC\):  
  
```  
//Microsoft Visual C++ generated resource script  
//  
#include "resource.h"  
```  
  
 RES\\MYAPP.RC2  
 Enthält Ressourcen, die mit Visual C\+\+ nicht bearbeitet werden, jedoch in der finalen kompilierten EXE\-Datei enthalten sind.  AppWizard erstellt solche Ressourcen nicht standardmäßig, da Visual C\+\+ alle Standardressourcen bearbeiten kann, einschließlich der Versionsressource \(eine neue Funktion in dieser Version\).  Von AppWizard wird eine leere Datei generiert, falls Sie dieser Datei eigene benutzerdefinierte formatierte Ressourcen hinzufügen möchten.  
  
 Wenn Sie benutzerdefinierte formatierte Ressourcen verwenden, können Sie sie zu RES\\MYAPP.RC2 hinzufügen und mit dem Visual C\+\+\-Text\-Editor bearbeiten.  
  
 AFXRES.RC und AFXPRINT.RC enthalten die Standardressourcen, die von bestimmten Funktionen des Frameworks benötigt werden.  Wie RES\\MYAPP.RC2 werden diese zwei vom Framework bereitgestellten Ressourcendateien mit \#include am Ende von MYAPP.RC eingebunden. Zudem werden sie in den Kompilierzeitdirektiven des Dialogfelds "Gruppe enthält" angegeben.  So werden diese Frameworkressourcen beim Bearbeiten von MYAPP.RC in Visual C\+\+ nicht direkt angezeigt oder bearbeitet, sie werden jedoch in die binäre RES\-Datei der Anwendung und die finale EXE\-Datei kompiliert.  Weitere Informationen über die Standardframeworkressourcen, einschließlich der Verfahren zum Ändern dieser Ressourcen, finden Sie unter [Technischer Hinweis 23](../mfc/tn023-standard-mfc-resources.md).  
  
 AFXRES.H definiert Standardsymbole, wie z. B. `ID_FILE_NEW`, die vom Framework und insbesondere in AFXRES.RC verwendet werden.  AFXRES.H bindet mit \#include auch die Datei WINRES.H ein, die eine Teilmenge von WINDOWS.H enthält. Diese wird von den von Visual C\+\+ generierten RC\-Dateien sowie AFXRES.RC benötigt.  Die in AFXRES.H definierten Symbole stehen beim Bearbeiten der Anwendungsressourcendatei \(MYAPP.RC\) zur Verfügung.  `ID_FILE_NEW` wird beispielsweise für das Menüelement "Neue Datei" in der Menüressource von MYAPP.RC verwendet.  Sie können diese vom Framework definierten Symbole nicht ändern oder löschen.  
  
 **Einschließen zusätzlicher Headerdateien**  
  
 Die von AppWizard erstellte Anwendung bindet nur zwei Headerdateien ein: RESOURCE.H und AFXRES.H.  Nur RESOURCE.H ist eine anwendungsspezifische Datei.  In folgenden Fällen müssen Sie möglicherweise zusätzliche schreibgeschützte Headerdateien einschließen:  
  
 Die Headerdatei wird von einer externen Quelle bereitgestellt, oder Sie möchten die Headerdatei für mehrere Projekte oder mehrere Bereiche desselben Projekts freigeben.  
  
 Die Headerdatei weist Formatierungen und Kommentare auf, die in Visual C\+\+ beim Speichern der Datei nicht geändert oder herausgefiltert werden sollen.  So möchten Sie beispielsweise \#define\-Direktiven beibehalten, die eine symbolische Arithmetik wie die folgende verwenden:  
  
```  
#define RED 0  
#define BLUE 1  
#define GREEN 2  
#define ID_COLOR_BUTTON 1001  
#define ID_RED_BUTTON (ID_COLOR_BUTTON + RED)  
#define ID_BLUE_BUTTON (ID_COLOR_BUTTON + BLUE)  
#define ID_GREEN_BUTTON (ID_COLOR_BUTTON + GREEN)  
```  
  
 Sie können zusätzliche schreibgeschützte Headerdateien einbinden, indem Sie den Befehl **Ressourcenincludes** verwenden, um die \#include\-Anweisung als zweite Direktive für schreibgeschützte Symbole anzugeben, Beispiel:  
  
```  
#include "afxres.h"  
#include "second.h"  
```  
  
 Das neue Dateibeziehungsdiagramm sieht nun wie folgt aus:  
  
```  
               AFXRES.H         
RESOURCE.H     SECOND.H                      
      \       /                                
       \     /                                  
      MYAPP.RC     
          |                                  
          |                                
    RES\MYAPP.RC2    
    AFXRES.RC                     
    AFXPRINT.RC                   
```  
  
 **Freigeben einer Headerdatei für zwei RC\-Dateien**  
  
 Sie können eine Headerdatei für zwei RC\-Dateien freigeben, die sich in verschiedenen Projekten oder auch im selben Projekt befinden.  Dazu wenden Sie einfach die oben beschriebene Technik für Direktiven für schreibgeschützte Symbole auf beide RC\-Dateien an.  Wenn die beiden RC\-Dateien für unterschiedliche Anwendungen \(unterschiedliche Projekte\) gedacht sind, sieht das Ergebnis wie im folgenden Diagramm dargestellt aus:  
  
```  
     RESOURCE.H   AFXRES.H   RESOURCE.H    
    (for MYAPP1)  SECOND.H   (for MYAPP2)               
          \       /     \       /             
           \     /       \     /               
          MYAPP1.RC      MYAPP2.RC                   
           /    \        /     \                     
          /      \      /       \              
RES\MYAPP1.RC2  AFXRES.RC     RES\MYAPP2.RC2                
                AFXPRINT.RC                   
```  
  
 Der Fall, dass die zweite Headerdatei von zwei RC\-Dateien in derselben Anwendung \(im selben Projekt\) gemeinsam verwendet wird, wird nachfolgend erläutert.  
  
 **Verwenden von mehreren Ressourcendateien im selben Projekt**  
  
 Visual C\+\+ und der Ressourcencompiler unterstützen mehrere RC\-Dateien im selben Projekt, indem eine RC\-Datei mit \#include in eine andere eingebunden wird.  Mehrfache Schachtelung ist zulässig.  Es gibt verschiedene Gründe für das Aufteilen der Ressourcen des Projekts in mehrere RC\-Dateien:  
  
-   Es ist einfacher, eine große Anzahl von Ressourcen für mehrere Projektteammitglieder zu verwalten, wenn Sie die Ressourcen in mehrere RC\-Dateien aufteilen.  Wenn Sie ein Quellcodeverwaltungs\-Paket für das Auschecken von Dateien und das Einchecken von Änderungen verwenden, ermöglicht das Aufteilen der Ressourcen in mehrere RC\-Dateien Ihnen eine genauere Steuerung der Verwaltung von Änderungen an den Ressourcen.  
  
-   Wenn Sie Präprozessordirektiven wie "\#ifdef", "\#endif" und "\#define" für Teile der Ressourcen verwenden möchten, müssen Sie sie in schreibgeschützten Ressourcen isolieren, die vom Ressourcencompiler kompiliert werden.  
  
-   RC\-Komponentendateien werden in Visual C\+\+ schneller geladen und gespeichert als eine zusammengesetzte RC\-Datei.  
  
-   Wenn Sie eine Ressource mit einem Text\-Editor in einem lesbaren Format verwalten möchten, sollten Sie sie in einer RC\-Datei getrennt von der Datei speichern, die in Visual C\+\+ bearbeitet wird.  
  
-   Wenn Sie eine benutzerdefinierte Ressource in einem Binär\- oder Textformat speichern müssen, das von einem anderen spezialisierten Daten\-Editor interpretiert werden kann, sollten Sie sie in einer separaten RC\-Datei speichern, damit Visual C\+\+ das Format nicht in Hexadezimaldaten ändert.  Die WAV\-\(Audio\-\)Dateiressourcen im MFC Advanced Concepts\-Beispiel [SPEAKN](../top/visual-cpp-samples.md) sind ein gutes Beispiel.  
  
 Sie können mit \#include eine SECOND.RC in die Kompilierzeitdirektiven im Dialogfeld "Gruppe enthält" einbinden:  
  
```  
#include "res\myapp.rc2"  // non-Visual C++ edited resources  
#include "second.rc"  // THE SECOND .RC FILE  
  
#include "afxres.rc"  // Standard components  
#include "afxprint.rc"  // printing/print preview resources  
```  
  
 Das Ergebnis ist im folgenden Diagramm dargestellt:  
  
```  
RESOURCE.H     AFXRES.H                      
       \       /                                
        \     /                                  
       MYAPP.RC  
           |                                  
           |                                
     RES\MYAPP.RC2  
     SECOND.RC    
     AFXRES.RC                     
     AFXPRINT.RC                   
```  
  
 Mithilfe von Kompilierzeitdirektive können Sie die in Visual C\+\+ bearbeitbaren und nicht bearbeitbaren Ressourcen in mehreren RC\-Dateien organisieren. Einzige Aufgabe der MYAPP.RC\-"Masterdatei" ist dabei die Einbindung der übrigen RC\-Dateien mit \#include.  Wenn Sie eine MAK\-Datei eines Visual C\+\+\-Projekts verwenden, sollten Sie die RC\-"Masterdatei" in das Projekt einschließen, damit alle mit \#include eingebundenen Ressourcen mit der Anwendung kompiliert werden.  
  
 **Erzwingung von nicht bearbeitbaren Visual C\+\+\-Dateien**  
  
 Die von AppWizard erstellte Datei RES\\MYAPP.RC2 ist ein Beispiel für eine Datei mit Ressourcen, die *nicht* versehentlich in Visual C\+\+ eingelesen werden und dann mit Verlust der Formatierungsinformationen wieder ausgelesen werden sollen.  Um dies zu verhindern, fügen Sie die folgenden Zeilen am Anfang der Datei RES\\MYAPP.RC2 ein:  
  
```  
#ifdef APSTUDIO_INVOKED  
    #error this file is not editable by Visual C++  
#endif //APSTUDIO_INVOKED  
```  
  
 Wenn Visual C\+\+ die RC\-Datei kompiliert, werden sowohl **APSTUDIO\_INVOKED** als auch **RC\_INVOKED** definiert.  Wenn die Struktur der von AppWizard erstellten Datei beschädigt ist und Visual C\+\+ die \#error\-Zeile oben liest, wird ein schwerwiegender Fehler gemeldet, und das Lesen der RC\-Datei wird abgebrochen.  
  
 **Verwalten von Symbolen, die von mehreren mit Visual C\+\+ bearbeiteten RC\-Dateien gemeinsam verwendet werden**  
  
 Es sind zwei Aspekte zu beachten, wenn Sie die Ressourcen in mehrere RC\-Dateien aufteilen, die Sie separat in Visual C\+\+ bearbeiten möchten:  
  
-   Sie möchten dieselben Symbole ggf. für mehrere RC\-Dateien verwenden.  
  
-   Sie müssen verhindern, dass Visual C\+\+ dieselben numerischen ID\-Werte unterschiedlichen Ressourcen \(Symbolen\) zuweist.  
  
 Das folgende Diagramm zeigt die Organisation von RC\- und H\-Dateien in Bezug auf den ersten Aspekt:  
  
```  
              MYAPP.RC  
             /         \  
            /           \  
MYSTRS.H   / MYSHARED.H  \  MYMENUS.H  
     \    /    /      \   \    \  
      \  /    /        \   \    \  
   MYSTRS.RC           MYMENUS.RC  
```  
  
 In diesem Beispiel werden Zeichenfolgenressourcen in der Ressourcendatei MYSTRS.RC und Menüs in der Ressourcendatei MYMENUS.RC gespeichert.  Einige Symbole, z. B. für Befehle, müssen möglicherweise in beiden Dateien genutzt werden.  Bei einem ID\_TOOLS\_SPELL\-Symbol kann es sich z. B. um die Menübefehl\-ID für das Spell\-Element in einem "Tools"\-Menü handeln. Es kann sich aber auch um die Zeichenfolgen\-ID der Eingabeaufforderung handeln, die vom Framework in der Statusleiste des Hauptfensters der Anwendung angezeigt wird.  
  
 Das ID\_TOOLS\_SPELL\-Symbol wird in der gemeinsam genutzten Headerdatei MYSHARED.H gespeichert.  Sie verwalten diese gemeinsam genutzte Headerdatei manuell mit einem Text\-Editor. Sie wird nicht direkt in Visual C\+\+ bearbeitet.  In den beiden Ressourcendateien MYSTRS.RC und MYMENUS.RC geben Sie \#include MYSHARED.H in den Direktiven für schreibgeschützte Symbole für MYAPP.RC an. Dazu verwenden Sie wie zuvor beschrieben den Befehl **Ressourcenincludes**.  
  
 Am einfachsten ist es, vorher zu überlegen, welches Symbol gemeinsam genutzt werden soll, bevor Sie versuchen, es zur Identifizierung einer Ressource zu verwenden.  Fügen Sie das Symbol der gemeinsam genutzten Headerdatei hinzu, sofern Sie die gemeinsam genutzte Headerdatei noch nicht mit \#include in die Direktiven für schreibgeschützte Symbole für die RC\-Datei eingebunden haben, bevor Sie das Symbol verwenden.  Wenn Sie sich nicht vorher überlegt haben, das Symbol auf diese Weise freizugeben, müssen Sie die \#define\-Anweisung für das Symbol manuell \(mithilfe eines Text\-Editors\) von z. B. MYMENUS.H in MYSHARED.H verschieben, bevor Sie sie in MYSTRS.RC verwenden.  
  
 Wenn Sie Symbole in mehreren RC\-Dateien verwalten, müssen Sie außerdem verhindern, dass Visual C\+\+ dieselben numerischen ID\-Werte unterschiedlichen Ressourcen \(Symbolen\) zuweist.  Für jede RC\-Datei weist Visual C\+\+ inkrementell IDs in jeder der vier ID\-Domänen zu.  Zwischen der Bearbeitung von Sitzungen verfolgt Visual C\+\+ die letzte ID, die in jeder der Domänen in der Symbolheaderdatei für die RC\-Datei zugewiesen wurde.  Nachfolgend sind die APS\_NEXT\-Werte für eine leere \(neue\) RC\-Datei aufgeführt:  
  
```  
#define _APS_NEXT_RESOURCE_VALUE  101  
#define _APS_NEXT_COMMAND_VALUE   40001  
#define _APS_NEXT_CONTROL_VALUE   1000  
#define _APS_NEXT_SYMED_VALUE     101  
```  
  
 **\_APS\_NEXT\_RESOURCE\_VALUE** ist der nächste Symbolwert, der für eine Dialogfeldressource, Menüressource usw. verwendet wird.  Der gültige Bereich für Ressourcensymbolwerte ist 1 bis 0x6FFF.  
  
 **\_APS\_NEXT\_COMMAND\_VALUE** ist der nächste Symbolwert, der für einen Befehlsbezeichner verwendet wird.  Der gültige Bereich für Befehlssymbolwerte ist 0x8000 bis 0xDFFF.  
  
 **\_APS\_NEXT\_CONTROL\_VALUE** ist der nächste Symbolwert, der für ein Dialogsteuerelement verwendet wird.  Der gültige Bereich für Symbolwerte für Dialogsteuerelemente ist 8 bis 0xDFFF.  
  
 **\_APS\_NEXT\_SYMED\_VALUE** ist der nächste Symbolwert, der ausgegeben wird, wenn Sie einen Symbolwert manuell mithilfe des Befehls "Neu" im Symbolbrowser zuweisen.  
  
 Visual C\+\+\-startet beim Erstellen einer neuen RC\-Datei mit Werten, die etwas höher sind als der niedrigste gültige Wert.  AppWizard initialisiert diese Werte zudem in einem Format, das für MFC\-Anwendungen geeignet ist.  Weitere Informationen über ID\-Wertbereiche finden Sie unter [Technischer Hinweis 20](../mfc/tn020-id-naming-and-numbering-conventions.md).  
  
 Visual C\+\+ definiert nun jedes Mal, wenn Sie eine neue Ressourcendatei erstellen \(auch innerhalb eines Projekts\) die gleichen **\_APS\_NEXT\_**\-Werte.  Das bedeutet, dass es z. B. beim Hinzufügen von mehreren Dialogfeldern in zwei verschiedenen RC\-Dateien sehr wahrscheinlich ist, dass der gleiche \#define\-Wert verschiedenen Dialogfeldern zugewiesen wird.  So kann IDD\_MY\_DLG1 in der ersten RC\-Datei beispielsweise die gleiche Zahl, 101, zugewiesen werden, wie IDD\_MY\_DLG2 in einer zweiten RC\-Datei.  
  
 Um dies zu vermeiden, sollten Sie einen separaten numerischen Bereich für jede der vier ID\-Domänen in den jeweiligen RC\-Dateien reservieren.  Dazu aktualisieren Sie manuell die **\_APS\_NEXT**\-Werte in jeder der RC\-Dateien, `before` Sie mit dem Hinzufügen von Ressourcen beginnen.  Wenn die erste RC\-Datei z. B. die standardmäßigen **\_APS\_NEXT**\-Werte verwendet, können Sie die folgenden **\_APS\_NEXT**\-Werte der zweiten RC\-Datei zuweisen:  
  
```  
#define _APS_NEXT_RESOURCE_VALUE  2000  
#define _APS_NEXT_COMMAND_VALUE   42000  
#define _APS_NEXT_CONTROL_VALUE   2000  
#define _APS_NEXT_SYMED_VALUE     2000  
```  
  
 Es ist natürlich immer noch möglich, dass Visual C\+\+ in der ersten RC\-Datei so viele IDs zuweist, dass die numerischen Werte die für die zweite RC\-Datei reservierten Werte überschneiden.  Sie sollten ausreichend große Bereiche reservieren, damit dies nicht geschieht.  
  
 **Verwalten von Abhängigkeiten zwischen RC\-, CPP\- und H\-Dateien**  
  
 Wenn Visual C\+\+ eine RC\-Datei speichert, werden auch Symboländerungen an der entsprechenden RESOURCE.H\-Datei gespeichert.  Alle CPP\-Dateien, die auf Ressourcen in der RC\-Datei verweisen, müssen mit \#include die RESOURCE.H\-Datei einbinden, normalerweise aus der Masterheaderdatei des Projekts.  Dies führt zu unerwünschten Nebeneffekten aufgrund des internen Projektmanagements der Entwicklungsumgebung, die Quelldateien auf Headerabhängigkeiten überprüft.  So müssten bei jedem Hinzufügen eines neuen Symbols in Visual C\+\+ alle CPP\-Dateien, die mit \#include RESOURCE.H einbinden, neu kompiliert werden.  
  
 Visual C\+\+ verhindert die Abhängigkeit von RESOURCE.H, indem der folgende Kommentar als erste Zeile der RESOURCE.H\-Datei hinzugefügt wird:  
  
```  
//{{NO_DEPENDENCIES}}  
```  
  
 Die Entwicklungsumgebung interpretiert diesen Kommentar, indem sie die Änderungen an RESOURCE.H ignoriert, damit abhängige CPP\-Dateien nicht neu kompiliert werden müssen.  
  
 Visual C\+\+ fügt immer die Kommentarzeile \/\/{{NO\_DEPENDENCIES}} zu einer RC\-Datei hinzu, wenn die Datei gespeichert wird.  In einigen Fällen führt das Umgehen der Buildabhängigkeit von RESOURCE.H möglicherweise zu Laufzeitfehlern, die zum Zeitpunkt der Verknüpfung unentdeckt bleiben.  Wenn Sie beispielsweise den Symbolbrowser zum Ändern des numerischen Werts verwenden, der einem Symbol für eine Ressource zugewiesen ist, wird die Ressource zur Anwendungslaufzeit möglicherweise nicht gefunden und ordnungsgemäß geladen, wenn die CPP\-Datei, die auf die Ressource verweist, nicht neu kompiliert wird.  In solchen Fällen sollten Sie alle CPP\-Dateien, die Ihrer Kenntnis nach von den Symboländerungen in RESOURCE.H betroffen sind, explizit neu kompilieren oder **Alles neu erstellen** auswählen.  Wenn Sie Symbolwerte für eine bestimmte Gruppe von Ressourcen häufig ändern müssen, ist es wahrscheinlich einfacher und sicherer, diese Symbole in eine separate schreibgeschützte Headerdatei auszugliedern, wie im obigen Abschnitt [Einschließen zusätzlicher Headerdateien](#_mfcnotes_tn035_including) beschrieben.  
  
 **Verwalten von "Gruppe enthält"\-Informationen in Visual C\+\+**  
  
 Wie oben erläutert, können Sie mit dem "Gruppe enthält"\-Befehl im Menü "Datei" drei Typen von Informationen angeben:  
  
-   Symbolheaderdatei  
  
-   Direktiven für schreibgeschützte Symbole  
  
-   Kompilierzeitdirektiven  
  
 Im Folgenden wird beschrieben, wie Visual C\+\+ diese Informationen in einer RC\-Datei verwaltet.  Sie benötigen diese Informationen nicht für die Verwendung von Visual C\+\+. Sie dienen jedoch einem besseren Verständnis, damit Sie im Umgang mit der Funktion "Gruppe enthält" sicherer werden.  
  
 Alle drei oben erwähnten Typen von "Gruppe enthält"\-Informationen werden in zwei Formen in der RC\-Datei gespeichert: \(1\) als \#include\- oder andere Direktiven, die vom Ressourcencompiler interpretiert werden können, und \(2\) als besondere TEXTINCLUDE\-Ressourcen, die nur von Visual C\+\+ interpretiert werden können.  
  
 Der Zweck der TEXTINCLUDE\-Ressource besteht im sicheren Speichern der "Gruppe enthält"\-Informationen in einer Form, die im Dialogfeld **Gruppe enthält** von Visual C\+\+ leicht darstellbar ist.  TEXTINCLUDE ist ein von Visual C\+\+ definierter *Ressourcentyp*.  Visual C\+\+ erkennt drei spezifische TEXTINCLUDE\-Ressourcen, die die Ressourcen\-IDs 1, 2 und 3 aufweisen:  
  
|TEXTINCLUDE\-Ressourcen\-ID|Typ der "Gruppe enthält"\-Informationen|  
|---------------------------------|---------------------------------------------|  
|1|Symbolheaderdatei|  
|2|Direktiven für schreibgeschützte Symbole|  
|3|Kompilierzeitdirektiven|  
  
 Alle drei Typen von "Gruppe enthält"\-Informationen werden in den von AppWizard erstellten MYAPP.RC\- und RESOURCE.H\-Standarddateien dargestellt, wie nachfolgend beschrieben.  Die zusätzlichen Token \\0 und "" zwischen den BEGIN\- und END\-Blöcken werden von der RC\-Syntax benötigt, um mit 0 endende Zeichenfolgen bzw. das doppelte Anführungszeichen anzugeben.  
  
## Symbolheaderdatei  
 Bei der Form der Symbolheaderdatei\-Informationen, die vom Ressourcencompiler interpretiert werden, handelt es sich um eine einfache \#include\-Anweisung:  
  
```  
#include "resource.h"  
```  
  
 Die entsprechende TEXTINCLUDE\-Ressource ist:  
  
```  
1 TEXTINCLUDE DISCARDABLE  
BEGIN  
   "resource.h\0"  
END  
```  
  
## Direktiven für schreibgeschützte Symbole  
 Direktiven für schreibgeschützte Symbole werden oben in der MYAPP.RC in der folgenden vom Ressourcencompiler interpretierbaren Form eingefügt:  
  
```  
#include "afxres.h"  
```  
  
 Die entsprechende TEXTINCLUDE\-Ressource ist:  
  
```  
2 TEXTINCLUDE DISCARDABLE  
BEGIN  
   "#include ""afxres.h""\r\n"  
   "\0"  
END  
```  
  
## Kompilierzeitdirektiven  
 Kompilierzeitdirektiven werden am Ende der MYAPP.RC in der folgenden vom Ressourcencompiler interpretierbaren Form eingefügt:  
  
```  
#ifndef APSTUDIO_INVOKED  
///////////////////////  
//  
// From TEXTINCLUDE 3  
//  
#include "res\myapp.rc2"  // non-Visual C++ edited resources  
  
#include "afxres.rc"  // Standard components  
#include "afxprint.rc"  // printing/print preview resources  
#endif  // not APSTUDIO_INVOKED  
```  
  
 Die \#ifndef APSTUDIO\_INVOKED\-Direktive weist Visual C\+\+ an, Kompilierzeitdirektiven zu überspringen.  
  
 Die entsprechende TEXTINCLUDE\-Ressource ist:  
  
```  
3 TEXTINCLUDE DISCARDABLE  
BEGIN  
"#include ""res\myapp.rc2""  // non-Visual C++ edited resources\r\n"  
"\r\n"  
"#include ""afxres.rc""  // Standard components\r\n"  
"#include ""afxprint.rc""  // printing/print preview resources\r\n"  
"\0"  
END  
```  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)