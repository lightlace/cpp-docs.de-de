---
title: "Exemplarische Vorgehensweise: Erstellen und Verwenden einer Dynamic Link Library (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLLs [C++], Exemplarische Vorgehensweisen"
  - "Bibliotheken [C++], DLLs"
ms.assetid: 3ae94848-44e7-4955-bbad-7d40f493e941
caps.latest.revision: 36
caps.handback.revision: "29"
ms.author: "corob"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Erstellen und Verwenden einer Dynamic Link Library (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In dieser schrittweisen exemplarischen Vorgehensweise wird die Erstellung einer DLL \(Dynamic Link Library\) zur Verwendung mit einer App in C\+\+ erläutert.  Die Verwendung einer Bibliothek stellt eine gute Möglichkeit zur Wiederverwendung von Code dar.  Anstatt die gleichen Routinen in jedem von Ihnen erstellten Programm erneut zu implementieren, schreiben Sie die Routinen einmal und verweisen dann in allen Apps, die diese Funktionen benötigen, darauf.  Halten Sie bei Eingabe von Code in die DLL in jeder App, die darauf verweist, etwas Platz frei, dann können Sie die DLL aktualisieren, ohne alle Apps neu kompilieren zu müssen.  Weitere Informationen über DLLs finden Sie unter [DLLs in Visual C\+\+](../build/dlls-in-visual-cpp.md).  
  
 In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben behandelt:  
  
-   Erstellen eines DLL\-Projekts  
  
-   Hinzufügen einer Klasse zu einer DLL  
  
-   Erstellen einer Konsolenanwendung, die zum Verweisen von DLLs dynamische Verknüpfung zur Ladezeit nutzt.  
  
-   Verwenden von Funktionen der Klasse in der App.  
  
-   Ausführen der App  
  
 In dieser exemplarischen Vorgehensweise wird eine DLL erstellt, die nur von Apps aufgerufen werden kann, die C\+\+\-Aufrufkonventionen verwenden.  Informationen zum Erstellen von DLLs mit anderen Sprachen finden Sie unter [Aufrufen von DLL\-Funktionen aus Visual Basic\-Anwendungen heraus](../build/calling-dll-functions-from-visual-basic-applications.md).  
  
## Vorbereitungsmaßnahmen  
 In diesem Thema wird davon ausgegangen, dass Sie die Grundlagen der Programmiersprache C\+\+ beherrschen.  
  
### So erstellen Sie ein Dynamic Link Library \(DLL\)\-Projekt  
  
1.  Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt** aus.  
  
2.  Erweitern Sie im linken Bereich des Dialogfeld **Neues Projekt** unter **Installiert**, **Vorlagen**, **Visual C\+\+**, und wählen Sie **Win32** aus.  
  
3.  Wählen Sie im mittleren Bereich **Win32\-Konsolenanwendung** aus.  
  
4.  Geben Sie im Feld **Name** einen Namen für das Projekt ein, z. B. "MathFuncsDll".  Geben Sie im Feld **Projektmappenname** einen Namen für die Projektmappe ein, z. B. "DynamicLibrary".  Klicken Sie auf die Schaltfläche **OK**.  
  
5.  Wählen Sie auf der Seite **Übersicht** des Dialogfelds **Win32\-Anwendungs\-Assistent** die Schaltfläche **Weiter**.  
  
6.  Wählen Sie auf der Seite **Anwendungseinstellungen** unter **Anwendungstyp** die Option **DLL** aus.  
  
7.  Wählen Sie die Schaltfläche **Fertig stellen**, um das Projekt zu erstellen.  
  
### So fügen Sie der Dynamic Link Library eine Klasse hinzu  
  
1.  Um eine Headerdatei für eine neue Klasse zu erstellen, wählen Sie auf der Menüleiste **Projekt**, **Neues Element hinzufügen** aus.  Wählen Sie im linken Bereich des Dialogfelds **Neues Element hinzufügen** unter **Visual C\+\+** die Option **Code** aus.  Wählen Sie im mittleren Bereich die Option **Headerdatei \(.h\)**.  Geben Sie einen Namen für die Headerdatei an, z. B. "MathFuncsDll.h", und wählen Sie die Schaltfläche **Hinzufügen** aus.  Eine leere Headerdatei wird angezeigt.  
  
2.  Fügen Sie dem Anfang der Headerdatei den folgenden Code hinzu:  
  
     [!CODE [NVC_Create_DLL_Walkthrough#100](../CodeSnippet/VS_Snippets_Cpp/nvc_create_dll_walkthrough#100)]  
  
3.  Fügen Sie eine Basisklasse mit dem Namen "MyMathFuncs" hinzu, die zur Ausführung der geläufigen mathematischen Operationen wie Addition, Subtraktion, Multiplikation und Division dient.  Der Code sollte diesem ähneln:  
  
     [!CODE [NVC_Create_DLL_Walkthrough#101](../CodeSnippet/VS_Snippets_Cpp/nvc_create_dll_walkthrough#101)]  
  
     Wenn das Symbol "MATHFUNCSDLL\_EXPORTS" definiert ist, wird das Symbol "MATHFUNCSDLL\_API" den `__declspec(dllexport)`\-Modifizierer in den Memberfunktionsdeklarationen in diesem Code festlegen.  Dieser Modifizierer ermöglicht den Export der Funktion durch die DLL, sodass sie in anderen Anwendungen verwendet werden kann.  Wenn MATHFUNCSDLL\_EXPORTS undefiniert ist, beispielsweise wenn die Headerdatei in einer Anwendung enthalten ist, definiert MATHFUNCSDLL\_API den `__declspec(dllimport)`\-Modifizierer in den Memberfunktionsdeklarationen.  Dieser Modifizierer optimiert den Import der Funktion in eine Anwendung.  Standardmäßig fügt die Vorlage für ein neues Projekt für eine DLL `PROJECTNAME`\_EXPORTS zu den definierten Symbolen für das DLL\-Projekt hinzu.  In diesem Beispiel wird MATHFUNCSDLL\_EXPORTS bei Erstellung des MathFuncsDll\-Projekts definiert.  Weitere Informationen finden Sie unter [dllexport, dllimport](../cpp/dllexport-dllimport.md).  
  
    > [!NOTE]
    >  Wenn Sie das DLL\-Projekt in der Befehlszeile erstellen, verwenden Sie die **\/D**\-Compileroption zum Definieren des "MATHFUNCSDLL\_EXPORTS"\-Symbols.  
  
4.  Öffnen Sie im Projekt **MathFuncsDll** im **Projektmappen\-Explorer** im Ordner **Quelldateien** das Element "MathFuncsDll.cpp".  
  
5.  Implementieren Sie die Funktionalität von MyMathFuncs in der Quelldatei.  Der Code sollte diesem ähneln:  
  
     [!CODE [NVC_Create_DLL_Walkthrough#110](../CodeSnippet/VS_Snippets_Cpp/nvc_create_dll_walkthrough#110)]  
  
6.  Kompilieren Sie die DLL \(Dynamic Link Library\), indem Sie auf der Menüleiste **Erstellen**, **Projektmappe erstellen** auswählen.  
  
    > [!NOTE]
    >  Wenn Sie eine Express Edition verwenden, bei der kein Menü **Erstellen** auf der Menüleiste angezeigt wird, wählen Sie **Tools**, **Einstellungen** und **Erweiterte Einstellungen** aus, um es zu aktivieren, und wählen Sie dann **Erstellen**, **Projektmappe erstellen** aus.  
  
    > [!NOTE]
    >  Verwenden Sie beim Erstellen eines Projekts an der Befehlszeile die **\/LD**\-Compileroption, um anzugeben, dass als Ausgabedatei eine DLL erstellt werden soll.  Weitere Informationen finden Sie unter [\/MD, \/MT, \/LD \(Laufzeitbibliothek verwenden\)](../build/reference/md-mt-ld-use-run-time-library.md).  Verwenden Sie die Compileroption **\/EHsc**, um die Ausnahmebehandlung bei C\+\+ zu aktivieren.  Weitere Informationen finden Sie unter [\/EH \(Ausnahmebehandlungsmodell\)](../build/reference/eh-exception-handling-model.md).  
  
### So erstellen Sie eine App, die eine DLL verweist  
  
1.  Um eine App in C\+\+ zu erstellen, die auf die gerade auf der Menüleiste erstellte DLL verweist und sie verwendet, wählen Sie **Datei**, **Neu** und dann **Projekt** aus.  
  
2.  Wählen Sie im linken Bereich unter **Visual C\+\+** die Option **Win32** aus.  
  
3.  Wählen Sie im mittleren Bereich **Win32\-Konsolenanwendung** aus.  
  
4.  Geben Sie im Feld **Name** einen Namen für das Projekt ein, z. B. "MyExecRefsDll".  Wählen Sie in der Dropdownliste neben **Projektmappe** die Option **Hinzufügen** aus.  Dadurch wird das neue Projekt der gleichen Projektmappe hinzugefügt, in der die DLL enthalten ist.  Klicken Sie auf die Schaltfläche **OK**.  
  
5.  Wählen Sie auf der Seite **Übersicht** des Dialogfelds **Win32\-Anwendungs\-Assistent** die Schaltfläche **Weiter**.  
  
6.  Wählen Sie auf der Seite **Anwendungseinstellungen** unter **Anwendungstyp** die Option **Konsolenanwendung** aus.  
  
7.  Deaktivieren Sie auf der Seite **Anwendungseinstellungen** unter **Zusätzliche Optionen** das Kontrollkästchen **Vorkompilierter Header**.  
  
8.  Wählen Sie die Schaltfläche **Fertig stellen**, um das Projekt zu erstellen.  
  
### So verwenden Sie die Funktionalität der Klassenbibliothek in der App  
  
1.  Nach dem Erstellen einer Konsolenanwendung wird ein leeres Programm für Sie erstellt.  Die Quelldatei erhält denselben Namen, den Sie zuvor ausgewählt haben.  In diesem Beispiel erhält die Quelldatei den Namen MyExecRefsDll.cpp.  
  
2.  Um die in der DLL erstellten mathematischen Routinen in der App zu verwenden, müssen Sie auf die Bibliothek verweisen.  Wählen Sie hierzu das Projekt "MyExecRefsDll" im **Projektmappen\-Explorer** aus, und wählen Sie dann auf der Menüleiste **Projekt**, **Verweise** aus.  Erweitern Sie im Dialogfeld **Eigenschaftenseiten** den Knoten **Allgemeine Eigenschaften**, wählen Sie **Framework und Verweise** aus, und wählen Sie dann die Schaltfläche **Neuen Verweis hinzufügen** aus.  Weitere Informationen zum Dialogfeld **Verweise** finden Sie unter [Hinzufügen von Verweisen](../ide/adding-references-in-visual-cpp-projects.md).  
  
3.  Im Dialogfeld **Verweis hinzufügen** werden Bibliotheken aufgeführt, auf die Sie verweisen können.  Auf der Registerkarte **Projekt** werden alle Projekte in der aktuellen Projektmappe und darin enthaltenen Bibliotheken aufgelistet.  Aktivieren Sie auf der Registerkarte **Projekte** das Kontrollkästchen neben "MathFuncsDll", und wählen Sie dann die Schaltfläche **OK** aus.  
  
4.  Um auf die Headerdateien der DLL zu verweisen, müssen Sie den enthaltenen Verzeichnispfad ändern.  Erweitern Sie dazu im Dialogfeld **Eigenschaftenseiten** den Knoten **Konfigurationseigenschaften**, erweitern Sie den Knoten **C\/C\+\+**, und wählen Sie dann **Allgemein** aus.  Geben Sie neben **Zusätzliche Includeverzeichnisse** den Pfad des Speicherorts der Headerdatei MathFuncsDll.h ein.  Sie können einen relativen Pfad, z. B. ..\\MathFuncsDll\\, verwenden, wählen Sie dann die Schaltfläche **OK** aus.  
  
5.  Nun können Sie die MyMathFuncs\-Klasse in dieser Anwendung verwenden.  Ersetzen Sie den Inhalt von MyExecRefsDll.cpp durch folgenden Code:  
  
     [!CODE [NVC_Create_DLL_Walkthrough#120](../CodeSnippet/VS_Snippets_Cpp/nvc_create_dll_walkthrough#120)]  
  
6.  Erstellen Sie die ausführbare Datei, indem Sie auf der Menüleiste **Erstellen**, **Projektmappe erstellen** auswählen.  
  
### So führen Sie die Anwendung aus  
  
1.  Stellen Sie sicher, dass "MyExecRefsDll" als Standardprojekt ausgewählt ist.  Wählen Sie im **Projektmappen\-Explorer** das Projekt "MyExecRefsDll" aus, und wählen Sie dann auf der Menüleiste die Option **Projekt**, **Als Startprojekt festlegen** aus.  
  
2.  Wählen Sie zum Ausführen des Projekts auf der Menüleiste **Debuggen**, **Starten ohne Debugging** aus.  Die Ausgabe sollte dieser Ausgabe ähneln:  
  
  **a \+ b \= 106,4**  
**a – b \= – 91,6**  
**a \* b \= 732,6**  
**a \/ b \= 0,0747475**  
**Abgefangene Ausnahme: b darf nicht 0 \(null\) sein\!**  
  
## Siehe auch  
 [Visual C\+\+ Guided Tour](assetId:///499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [DLLs in Visual C\+\+](../build/dlls-in-visual-cpp.md)   
 [Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Exemplarische Vorgehensweise: Bereitstellen des Programms \(C\+\+\)](../ide/walkthrough-deploying-your-program-cpp.md)   
 [Aufrufen von DLL\-Funktionen aus Visual Basic\-Anwendungen heraus](../build/calling-dll-functions-from-visual-basic-applications.md)