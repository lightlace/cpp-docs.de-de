---
title: 'Exemplarische Vorgehensweise: Erstellen und Verwenden einer statischen Bibliothek (C++)'
ms.custom: get-started-article
ms.date: 09/18/2018
helpviewer_keywords:
- libraries [C++], static
- static libraries [C++]
ms.assetid: 3cc36411-7d66-4240-851e-dacb9a8fd6ac
ms.author: corob
ms.openlocfilehash: 506db5ea8e94887d9971b48c06ce8c0d6156dccb
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785086"
---
# <a name="walkthrough-creating-and-using-a-static-library-c"></a>Exemplarische Vorgehensweise: Erstellen und Verwenden einer statischen Bibliothek (C++)

In dieser schrittweise erläuterten exemplarischen Vorgehensweise wird die Erstellung einer statischen Bibliothek (LIB-Datei) für die Verwendung mit C++-Apps erläutert. Die Verwendung einer statischen Bibliothek stellt eine gute Möglichkeit zur Wiederverwendung von Code dar. Anstatt die gleichen Routinen in jede app, die die Funktionalität ist erforderlich, Sie schreiben eine neuimplementierung Zeit in einer statischen Bibliothek aus, und dann aus den apps darauf verweisen. Der Code, der von einer statischen Bibliothek verknüpft ist, wird Teil der App. Sie müssen keine andere Datei installieren, um den Code zu verwenden.

In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben behandelt:

- [Erstellen eines statischen Bibliotheksprojekts](#CreateLibProject)

- [Hinzufügen einer Klasse zur statischen Bibliothek](#AddClassToLib)

- [Erstellen einer Konsolenanwendung in C++, die auf die statische Bibliothek verweist](#CreateAppToRefTheLib)

- [Verwenden der Funktionalität der statischen Bibliothek in der App](#UseLibInApp)

- [Ausführen der App](#RunApp)

## <a name="prerequisites"></a>Vorraussetzungen

Grundlegende Kenntnisse der Programmiersprache C++.

##  <a name="CreateLibProject"></a> Erstellen eines statischen Bibliotheksprojekts

### <a name="to-create-a-static-library-project"></a>So erstellen Sie ein statisches Bibliotheksprojekt

1. Klicken Sie in der Menüleiste auf **Datei** > **Neu** > **Projekt**.

1. Im linken Bereich die **neues Projekt** Dialogfeld erweitern Sie **installiert** > **Visual C++**, und wählen Sie dann **Windows Desktop**. Wählen Sie im mittleren Bereich **-Assistenten für Windows Desktop**.

   > [!NOTE]
   > Für Versionen von Visual Studio, die älter als 2017 in der **neues Projekt** Dialogfeld erweitern Sie **installiert** > **Vorlagen**  >  **Visual C++**, und wählen Sie dann **Win32**. Wählen Sie im mittleren Bereich **Win32-Konsolenanwendung**aus.

1. Geben Sie im Feld *Name*einen Namen für das Projekt ein, z. B. **MathFuncsLib** . Geben Sie im Feld *Projektmappenname*einen Namen für die Projektmappe ein, z. B. **StaticLibrary** . Klicken Sie auf die Schaltfläche **OK** .

    - Für Visual Studio 2017

        1. Klicken Sie unter **Anwendungstyp**Option **statische Bibliothek (.lib)**.

        1. Klicken Sie unter **zusätzliche Optionen**, deaktivieren Sie die **vorkompilierter Header** Kontrollkästchen.

        1. Wählen Sie **OK** zum Erstellen des Projekts.

    - Für Versionen von Visual Studio, die älter als 2017

        1. Klicken Sie auf **Weiter**.

        1. Klicken Sie unter **Anwendungstyp**Option **statische Bibliothek**. Deaktivieren Sie die **vorkompilierter Header** und **Fertig stellen**.

##  <a name="AddClassToLib"></a> Hinzufügen einer Klasse zur statischen Bibliothek

### <a name="to-add-a-class-to-the-static-library"></a>So fügen Sie der statischen Bibliothek eine Klasse hinzu

1. Zum Erstellen einer Headerdatei für eine neue Klasse öffnen Sie das Kontextmenü für die **MathFuncsLib** Projekt **Projektmappen-Explorer**, und wählen Sie dann **hinzufügen**  >   **Neues Element**. Wählen Sie im linken Bereich des Dialogfelds **Neues Element hinzufügen** unter **Visual C++** die Option **Code**aus. Wählen Sie im mittleren Bereich die Option **Headerdatei (.h)**. Geben Sie einen Namen für die Headerdatei an, z. B. *MathFuncsLib.h*, und wählen Sie die Schaltfläche **Hinzufügen** aus. Eine leere Headerdatei wird angezeigt.

1. Fügen Sie eine Klasse, die mit dem Namen `MyMathFuncs` zu geläufigen mathematischen Operationen wie Addition, Subtraktion, Multiplikation und Division. Der Code in etwa:

   [!code-cpp[NVC_Walkthrough_Create_Static_Lib#100](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_1.h)]

1. Zum Erstellen einer Quelldatei für die neue Klasse öffnen Sie das Kontextmenü für die **MathFuncsLib** Projekt **Projektmappen-Explorer**, und wählen Sie dann **hinzufügen**  >   **Neues Element**. Wählen Sie im linken Bereich des Dialogfelds **Neues Element hinzufügen** unter **Visual C++** die Option **Code**aus. Wählen Sie im mittleren Bereich die Option **C++-Datei (.cpp)**. Geben Sie einen Namen für die Quelldatei an, z. B. *MathFuncsLib.cpp*, und wählen Sie die Schaltfläche **Hinzufügen** aus. Eine leere Quelldatei wird angezeigt.

1. Verwenden Sie diese Quelldatei zum Implementieren der Funktionalität von **MyMathFuncs**. Der Code in etwa:

   [!code-cpp[NVC_Walkthrough_Create_Static_Lib#110](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_2.cpp)]

1. Kompilieren Sie die statische Bibliothek dazu **erstellen** > **Projektmappe** in der Menüleiste. Beim Kompilieren erstellt eine statische Bibliothek, die von anderen Programmen verwendet werden kann.

   > [!NOTE]
   > Beim Erstellen über die Befehlszeile von Visual Studio müssen Sie das Programm in zwei Schritten erstellen. Führen Sie zunächst `cl /c /EHsc MathFuncsLib.cpp` zum Kompilieren des Codes und Erstellen einer Objektdatei mit dem Namen `MathFuncsLib.obj`. (Mit dem `cl`-Befehl wird der Compiler, "Cl.exe", aufgerufen, und mit der `/c`-Option wird Kompilieren ohne zu verknüpfen angegeben. Weitere Informationen finden Sie unter [/c (Kompilieren ohne Verknüpfen)](../build/reference/c-compile-without-linking.md).) Führen Sie `lib MathFuncsLib.obj` zum Verknüpfen des Codes und Erstellen der statischen Bibliothek `MathFuncsLib.lib`. (Mit dem `lib` Befehl wird der Bibliotheks-Manager, "Lib.exe", aufgerufen. Weitere Informationen finden Sie unter [LIB Reference](../build/reference/lib-reference.md).)

##  <a name="CreateAppToRefTheLib"></a> Erstellen einer Konsolenanwendung in C++, die auf die statische Bibliothek verweist

### <a name="to-create-a-c-console-app-that-references-the-static-library"></a>So erstellen Sie eine Konsolenanwendung in C++, die auf die statische Bibliothek verweist

1. Klicken Sie in der Menüleiste auf **Datei** > **Neu** > **Projekt**.

1. Im linken Bereich die **neues Projekt** Dialogfeld erweitern Sie **installiert** > **Visual C++**, und wählen Sie dann **Windows Desktop**. Wählen Sie im mittleren Bereich **-Assistenten für Windows Desktop**.

   > [!NOTE]
   > Für Versionen von Visual Studio, die älter als 2017 in der **neues Projekt** Dialogfeld erweitern Sie **installiert** > **Vorlagen**  >  **Visual C++**, und wählen Sie dann **Win32**. Wählen Sie im mittleren Bereich **Win32-Konsolenanwendung**aus.

1. Geben Sie im Feld *Name*einen Namen für das Projekt ein, z. B. **MyExecRefsLib** . Wählen Sie in der Dropdownliste neben **Projektmappe**die Option **Hinzufügen**aus. Der Befehl fügt das neue Projekt der Projektmappe, die die statische Bibliothek enthält. Klicken Sie auf die Schaltfläche **OK** .

    - Für Visual Studio 2017

        1. Klicken Sie unter **Anwendungstyp**Option **Konsolenanwendung (.exe)**.

        1. Klicken Sie unter **zusätzliche Optionen**, deaktivieren Sie die **vorkompilierter Header** Kontrollkästchen.

        1. Wählen Sie **OK** zum Erstellen des Projekts.

    - Für Versionen von Visual Studio, die älter als 2017

        1. Klicken Sie auf **Weiter**.

        1. Stellen Sie sicher, dass **Konsolenanwendung** ausgewählt ist. Überprüfen Sie dann die **leeres Projekt** und **Fertig stellen**.

##  <a name="UseLibInApp"></a> Verwenden der Funktionalität der statischen Bibliothek in der App

### <a name="to-use-the-functionality-from-the-static-library-in-the-app"></a>So verwenden Sie die Funktionalität der statischen Bibliothek in der App

1. Nach dem Erstellen einer Konsolenanwendung wird ein leeres Programm für Sie erstellt. Die Quelldatei erhält denselben Namen, den Sie zuvor ausgewählt haben. Im Beispiel heißt es `MyExecRefsLib.cpp`.

1. Bevor Sie die mathematischen Routinen verwenden können, müssen Sie auf die erstellte statische Bibliothek verweisen. Öffnen Sie das Kontextmenü für die **MyExecRefsLib** Projekt **Projektmappen-Explorer**, und wählen Sie dann **hinzufügen** > **Verweis**.

1. Im Dialogfeld **Verweis hinzufügen** werden Bibliotheken aufgeführt, auf die Sie verweisen können. Die **Projekte** Registerkarte listet die Projekte in der aktuellen Projektmappe und alle Bibliotheken, die sie verweisen. Aktivieren Sie auf der Registerkarte **Projekte** das Kontrollkästchen **MathFuncsLib** aus, und wählen Sie dann die Schaltfläche **OK** aus.

1. Verweis der `MathFuncsLib.h` -Headerdatei müssen Sie den enthaltenen Verzeichnispfad ändern. Erweitern Sie im Dialogfeld **Eigenschaftenseiten** von **MyExecRefsLib**den Knoten **Konfigurationseigenschaften** , erweitern Sie den Knoten **C/C++** , und wählen Sie dann **Allgemein**aus. Neben **Additional Include Directories**, geben Sie den Pfad, der die **MathFuncsLib** Verzeichnis, oder suchen Sie danach.

   Um nach dem Verzeichnispfad zu suchen, öffnen Sie die Dropdownliste für Eigenschaftswerte, und wählen Sie dann **Bearbeiten**aus. In der **Additional Include Directories** Dialogfeld, in das Textfeld ein, wählen Sie eine leere Zeile, und wählen Sie dann die Schaltfläche mit den Auslassungspunkten (**...** ) am Ende der Zeile. Wählen Sie im Dialogfeld **Verzeichnis auswählen** das **MathFuncsLib** -Verzeichnis aus, und wählen Sie dann die **Ordner auswählen** -Schaltfläche aus, um die Auswahl zu speichern und das Dialogfeld zu schließen. Wählen Sie im Dialogfeld **Zusätzliche Includeverzeichnisse** die Schaltfläche **OK** aus, und wählen Sie dann im Dialogfeld **Eigenschaftenseiten** die Schaltfläche **OK** aus, um die Änderungen am Projekt zu speichern.

1. Können Sie jetzt die `MyMathFuncs` Klasse in dieser app durch Einschließen der `#include "MathFuncsLib.h"` Header in Ihrem Code. Ersetzen Sie den Inhalt der `MyExecRefsLib.cpp` durch den folgenden Code:

   [!code-cpp[NVC_Walkthrough_Create_Static_Lib#120](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_3.cpp)]

1. Erstellen Sie die ausführbare Datei durch Auswahl **erstellen** > **Projektmappe** in der Menüleiste.

##  <a name="RunApp"></a> Ausführen der App

### <a name="to-run-the-app"></a>So führen Sie die App aus

1. Stellen Sie sicher, dass **MyExecRefsLib** als Standardprojekt ausgewählt wurde. Öffnen Sie dazu das Kontextmenü von **MyExecRefsLib** im **Projektmappen-Explorer**, und wählen Sie anschließend **Als Startprojekt festlegen**aus.

1. Klicken Sie zum Ausführen des Projekts auf der Menüleiste auf **Debuggen** > **Starten ohne Debuggen**. Die Ausgabe in etwa:

    ```Output
    a + b = 106.4
    a - b = -91.6
    a * b = 732.6
    a / b = 0.0747475
    ```

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweise: Erstellen und Verwenden einer Dynamic Link Library (C++)](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)<br/>
[Desktopanwendungen (Visual C++)](../windows/desktop-applications-visual-cpp.md)<br/>
