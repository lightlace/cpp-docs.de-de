---
title: "Exemplarische Vorgehensweise: Erstellen und Verwenden einer statischen Bibliothek (C++)"
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
  - "Bibliotheken [C++], statische"
  - "Statische Bibliotheken [C++]"
ms.assetid: 3cc36411-7d66-4240-851e-dacb9a8fd6ac
caps.latest.revision: 38
caps.handback.revision: "38"
ms.author: "corob"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Erstellen und Verwenden einer statischen Bibliothek (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In dieser schrittweise erläuterten exemplarischen Vorgehensweise wird die Erstellung einer statischen Bibliothek \(LIB\-Datei\) für die Verwendung mit C\+\+\-Apps erläutert. Die Verwendung einer statischen Bibliothek stellt eine gute Möglichkeit zur Wiederverwendung von Code dar. Anstatt die gleichen Routinen in jeder von Ihnen erstellten App, für die diese Funktion erforderlich ist, erneut zu implementieren, schreiben Sie die Routinen einmal in eine statische Bibliothek und verweisen dann von den Apps darauf. Der Code, der von einer statischen Bibliothek verknüpft ist, wird Teil der App. Sie müssen keine andere Datei installieren, um den Code zu verwenden.  
  
 In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben behandelt:  
  
-   [Erstellen eines statischen Bibliotheksprojekts](#BKMK_CreateLibProject)  
  
-   [Hinzufügen einer Klasse zur statischen Bibliothek](#BKMK_AddClassToLib)  
  
-   [Erstellen einer Konsolenanwendung in C++, die auf die statische Bibliothek verweist](#BKMK_CreateAppToRefTheLib)  
  
-   [Verwenden der Funktionalität der statischen Bibliothek in der App](#BKMK_UseLibInApp)  
  
-   [Ausführen der App](#BKMK_RunApp)  
  
## Vorbereitungsmaßnahmen  
 Grundlegende Kenntnisse der Programmiersprache C\+\+.  
  
##  <a name="BKMK_CreateLibProject"></a> Erstellen eines statischen Bibliotheksprojekts  
  
#### So erstellen Sie ein statisches Bibliotheksprojekt  
  
1.  Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt** aus.  
  
2.  Erweitern Sie im linken Bereich des Dialogfeld **Neues Projekt** unter **Installiert**, **Vorlagen**, **Visual C\+\+**, und wählen Sie **Win32** aus.  
  
3.  Wählen Sie im mittleren Bereich **Win32\-Konsolenanwendung** aus.  
  
4.  Geben Sie im Feld **Name** einen Namen für das Projekt ein, z. B. **MathFuncsLib**. Geben Sie im Feld **Projektmappenname** einen Namen für die Projektmappe ein, z. B. **StaticLibrary**. Klicken Sie auf die Schaltfläche **OK**.  
  
5.  Wählen Sie auf der Seite **Übersicht** des Dialogfelds **Win32\-Anwendungs\-Assistent** die Schaltfläche **Weiter**.  
  
6.  Wählen Sie auf der Seite **Anwendungseinstellungen** unter **Anwendungstyp** die Option **Statische Bibliothek** aus.  
  
7.  Deaktivieren Sie auf der Seite **Anwendungseinstellungen** unter **Zusätzliche Optionen** das Kontrollkästchen **Vorkompilierter Header**.  
  
8.  Wählen Sie die Schaltfläche **Fertig stellen**, um das Projekt zu erstellen.  
  
##  <a name="BKMK_AddClassToLib"></a> Hinzufügen einer Klasse zur statischen Bibliothek  
  
#### So fügen Sie der statischen Bibliothek eine Klasse hinzu  
  
1.  Zum Erstellen einer Headerdatei für eine neue Klasse öffnen Sie das Kontextmenü für das **MathFuncsLib**\-Projekt im **Projektmappen\-Explorer**, und wählen Sie dann **Hinzufügen**, **Neues Element** aus. Wählen Sie im linken Bereich des Dialogfelds **Neues Element hinzufügen** unter **Visual C\+\+** die Option **Code** aus. Wählen Sie im mittleren Bereich die Option **Headerdatei \(.h\)**. Geben Sie einen Namen für die Headerdatei an, z. B. **MathFuncsLib.h**, und wählen Sie die Schaltfläche **Hinzufügen** aus. Eine leere Headerdatei wird angezeigt.  
  
2.  Fügen Sie eine Klasse mit dem Namen **MyMathFuncs** hinzu, die zur Ausführung der geläufigen mathematischen Operationen wie Addition, Subtraktion, Multiplikation und Division dient. Der Code sollte diesem ähneln:  
  
     [!CODE [NVC_Walkthrough_Create_Static_Lib#100](../CodeSnippet/VS_Snippets_Cpp/nvc_walkthrough_create_static_lib#100)]  
  
3.  Zum Erstellen einer Quelldatei für die neue Klasse öffnen Sie das Kontextmenü für das **MathFuncsLib**\-Projekt im **Projektmappen\-Explorer**, und wählen Sie dann **Hinzufügen**, **Neues Element** aus. Wählen Sie im linken Bereich des Dialogfelds **Neues Element hinzufügen** unter **Visual C\+\+** die Option **Code** aus. Wählen Sie im mittleren Bereich die Option **C\+\+\-Datei \(.cpp\)**. Geben Sie einen Namen für die Quelldatei an, z. B. **MathFuncsLib.cpp**, und wählen Sie die Schaltfläche **Hinzufügen** aus. Eine leere Quelldatei wird angezeigt.  
  
4.  Verwenden Sie diese Quelldatei zum Implementieren der Funktionalität von **MyMathFuncs**. Der Code sollte diesem ähneln:  
  
     [!CODE [NVC_Walkthrough_Create_Static_Lib#110](../CodeSnippet/VS_Snippets_Cpp/nvc_walkthrough_create_static_lib#110)]  
  
5.  Kompilieren Sie die statische Bibliothek, indem Sie in der Menüleiste **Erstellen** die Option **Projektmappe erstellen** auswählen. Dadurch wird eine statische Bibliothek erstellt, die in anderen Programmen verwendet werden kann.  
  
    > [!NOTE]
    >  Beim Erstellen über die Befehlszeile von Visual Studio müssen Sie das Programm in zwei Schritten erstellen. Führen Sie zum Kompilieren des Codes und Erstellen einer Objektdatei namens **MathFuncsLib.obj** zunächst **cl \/c \/EHsc MathFuncsLib.cpp** aus. \(Mit dem **cl**\-Befehl wird der Compiler, "Cl.exe", aufgerufen, und mit der **\/c**\-Option wird Kompilieren ohne zu verknüpfen angegeben. Weitere Informationen finden Sie unter [\/c \(Kompilieren ohne Verknüpfen\)](../build/reference/c-compile-without-linking.md).\) Führen sie zum Verknüpfen des Codes und zum Erstellen der statischen Bibliothek **MathFuncsLib.lib** als Zweites **lib MathFuncsLib.obj** aus. \(Mit dem **lib** Befehl wird der Bibliotheks\-Manager, "Lib.exe", aufgerufen. Weitere Informationen finden Sie unter [LIB\-Referenz](../build/reference/lib-reference.md).\)  
  
##  <a name="BKMK_CreateAppToRefTheLib"></a> Erstellen einer Konsolenanwendung in C\+\+, die auf die statische Bibliothek verweist  
  
#### So erstellen Sie eine Konsolenanwendung in C\+\+, die auf die statische Bibliothek verweist  
  
1.  Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt** aus.  
  
2.  Wählen Sie im linken Bereich unter **Visual C\+\+** die Option **Win32** aus.  
  
3.  Wählen Sie im mittleren Bereich **Win32\-Konsolenanwendung** aus.  
  
4.  Geben Sie im Feld **Name** einen Namen für das Projekt ein, z. B. **MyExecRefsLib**. Wählen Sie in der Dropdownliste neben **Projektmappe** die Option **Hinzufügen** aus. Dadurch wird das neue Projekt in die Projektmappe eingefügt, in der auch die statische Bibliothek enthalten ist. Klicken Sie auf die Schaltfläche **OK**.  
  
5.  Wählen Sie auf der Seite **Übersicht** des Dialogfelds **Win32\-Anwendungs\-Assistent** die Schaltfläche **Weiter**.  
  
6.  Wählen Sie auf der Seite **Anwendungseinstellungen** unter **Anwendungstyp** die Option **Konsolenanwendung** aus.  
  
7.  Deaktivieren Sie auf der Seite **Anwendungseinstellungen** unter **Zusätzliche Optionen** das Kontrollkästchen **Vorkompilierter Header**.  
  
8.  Wählen Sie die Schaltfläche **Fertig stellen**, um das Projekt zu erstellen.  
  
##  <a name="BKMK_UseLibInApp"></a> Verwenden der Funktionalität der statischen Bibliothek in der App  
  
#### So verwenden Sie die Funktionalität der statischen Bibliothek in der App  
  
1.  Nach dem Erstellen einer Konsolenanwendung wird ein leeres Programm für Sie erstellt. Die Quelldatei erhält denselben Namen, den Sie zuvor ausgewählt haben. In diesem Beispiel erhält die Quelldatei den Namen **MyExecRefsLib.cpp**.  
  
2.  Bevor Sie die mathematischen Routinen verwenden können, müssen Sie auf die erstellte statische Bibliothek verweisen. Öffnen Sie dazu im **Projektmappen\-Explorer** das Kontextmenü für **MyExecRefsLib**, und wählen Sie dann den Knoten **Verweise** aus. Erweitern Sie im Dialogfeld **Eigenschaftenseiten** von **MyExecRefsLib** den Knoten **Allgemeine Eigenschaften**, wählen Sie **Framework und Verweise** aus, und wählen Sie dann die Schaltfläche **Neuen Verweis hinzufügen** aus. Weitere Informationen zum Dialogfeld **Verweise** finden Sie unter [Hinzufügen von Verweisen](../ide/adding-references-in-visual-cpp-projects.md).  
  
3.  Im Dialogfeld **Verweis hinzufügen** werden Bibliotheken aufgeführt, auf die Sie verweisen können. Auf der Registerkarte **Projekte** werden alle Projekte in der aktuellen Projektmappe und darin enthaltenen Bibliotheken aufgelistet. Aktivieren Sie auf der Registerkarte **Projekte** das Kontrollkästchen **MathFuncsLib** aus, und wählen Sie dann die Schaltfläche **OK** aus.  
  
4.  Um auf die Headerdatei **MathFuncsLib.h** zu verweisen, müssen Sie den enthaltenen Verzeichnispfad ändern. Erweitern Sie im Dialogfeld **Eigenschaftenseiten** von **MyExecRefsLib** den Knoten **Konfigurationseigenschaften**, erweitern Sie den Knoten **C\/C\+\+**, und wählen Sie dann **Allgemein** aus. Geben Sie neben **Zusätzliche Includeverzeichnisse** den Pfad des **MathFuncsLib**\-Verzeichnisses ein, oder suchen Sie danach.  
  
     Um nach dem Verzeichnispfad zu suchen, öffnen Sie die Dropdownliste für Eigenschaftswerte, und wählen Sie dann **Bearbeiten** aus. Wählen Sie im Dialogfeld **Zusätzliche Includeverzeichnisse** im Textfeld eine Leerzeile aus, und wählen Sie dann die Schaltfläche mit den Auslassungspunkten \(**...**\) am Ende der Linie aus. Wählen Sie im Dialogfeld **Verzeichnis auswählen** das **MathFuncsLib**\-Verzeichnis aus, und wählen Sie dann die **Ordner auswählen**\-Schaltfläche aus, um die Auswahl zu speichern und das Dialogfeld zu schließen. Wählen Sie im Dialogfeld **Zusätzliche Includeverzeichnisse** die Schaltfläche **OK** aus, und wählen Sie dann im Dialogfeld **Eigenschaftenseiten** die Schaltfläche **OK** aus, um die Änderungen am Projekt zu speichern.  
  
5.  Nun können Sie die **MyMathFuncs**\-Klasse in dieser App verwenden. Ersetzen Sie dazu den Inhalt von **MyExecRefsLib.cpp** durch den folgenden Code.  
  
     [!CODE [NVC_Walkthrough_Create_Static_Lib#120](../CodeSnippet/VS_Snippets_Cpp/nvc_walkthrough_create_static_lib#120)]  
  
6.  Erstellen Sie die ausführbare Datei, indem Sie auf der Menüleiste **Erstellen**, **Projektmappe erstellen** auswählen.  
  
##  <a name="BKMK_RunApp"></a> Ausführen der App  
  
#### So führen Sie die App aus  
  
1.  Stellen Sie sicher, dass **MyExecRefsLib** als Standardprojekt ausgewählt wurde. Öffnen Sie dazu das Kontextmenü von **MyExecRefsLib** im **Projektmappen\-Explorer**, und wählen Sie anschließend **Als Startprojekt festlegen** aus.  
  
2.  Wählen Sie zum Ausführen des Projekts auf der Menüleiste **Debuggen**, **Starten ohne Debugging** aus. Die Ausgabe sollte dieser Ausgabe ähneln:  
  
    ```Output  
    a + b = 106,4 a - b = -91,6 a * b = 732,6 a / b = 0,0747475  
    ```  
  
## Siehe auch  
 [Tour zu Visual C\+\+](assetId:///499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [Exemplarische Vorgehensweise: Erstellen und Verwenden einer Dynamic Link Library \(C\+\+\)](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)   
 [Windows\-Desktopanwendungen \(Visual C\+\+\)](../windows/desktop-applications-visual-cpp.md)