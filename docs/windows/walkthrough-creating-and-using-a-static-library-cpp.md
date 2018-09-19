---
title: 'Exemplarische Vorgehensweise: Erstellen und Verwenden einer statischen Bibliothek (C++) | Microsoft-Dokumentation'
ms.custom: get-started-article
ms.date: 07/12/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- libraries [C++], static
- static libraries [C++]
ms.assetid: 3cc36411-7d66-4240-851e-dacb9a8fd6ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4fb801e4f4cd39fba7f06e066ae0bf2f92e76a21
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601436"
---
# <a name="walkthrough-creating-and-using-a-static-library-c"></a>Exemplarische Vorgehensweise: Erstellen und Verwenden einer statischen Bibliothek (C++)

In dieser schrittweise erläuterten exemplarischen Vorgehensweise wird die Erstellung einer statischen Bibliothek (LIB-Datei) für die Verwendung mit C++-Apps erläutert. Die Verwendung einer statischen Bibliothek stellt eine gute Möglichkeit zur Wiederverwendung von Code dar. Anstatt die gleichen Routinen in jeder von Ihnen erstellten App, für die diese Funktion erforderlich ist, erneut zu implementieren, schreiben Sie die Routinen einmal in eine statische Bibliothek und verweisen dann von den Apps darauf. Der Code, der von einer statischen Bibliothek verknüpft ist, wird Teil der App. Sie müssen keine andere Datei installieren, um den Code zu verwenden.

In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben behandelt:

- [Erstellen eines statischen Bibliotheksprojekts](#CreateLibProject)

- [Hinzufügen einer Klasse zur statischen Bibliothek](#AddClassToLib)

- [Erstellen eine C++-Konsolen-app, die auf die statische Bibliothek verweist.](#CreateAppToRefTheLib)

- [Verwenden der Funktionalität der statischen Bibliothek in der app](#UseLibInApp)

- [Ausführen der app](#RunApp)

## <a name="prerequisites"></a>Erforderliche Komponenten

Grundlegende Kenntnisse der Programmiersprache C++.

##  <a name="CreateLibProject"></a> Erstellen eines statischen Bibliotheksprojekts

### <a name="to-create-a-static-library-project"></a>So erstellen Sie ein statisches Bibliotheksprojekt

1. Klicken Sie in der Menüleiste auf **Datei** > **Neu** > **Projekt**.

2. Im linken Bereich die **neues Projekt** Dialogfeld erweitern Sie **installiert, Visual C++**, und wählen Sie dann **Windows Desktop**.

3. Wählen Sie im mittleren Bereich **-Assistenten für Windows Desktop**.

4. Geben Sie einen Namen für das Projekt, z. B. *MathFuncsLib*– in der **Namen** Feld. Geben Sie einen Namen für die Lösung, z. B. *StaticLibrary*– in der **Projektmappenname** Feld. Klicken Sie auf die Schaltfläche **OK** .

5. Klicken Sie unter **Anwendungstyp**, wählen Sie die statische Bibliothek (.lib).

6. Klicken Sie unter **zusätzliche Optionen**, deaktivieren Sie die **vorkompilierter Header** Kontrollkästchen.

7. Wählen Sie **OK** zum Erstellen des Projekts.

##  <a name="AddClassToLib"></a> Hinzufügen einer Klasse zur statischen Bibliothek

### <a name="to-add-a-class-to-the-static-library"></a>So fügen Sie der statischen Bibliothek eine Klasse hinzu

1. Zum Erstellen einer Headerdatei für eine neue Klasse öffnen Sie das Kontextmenü für das **MathFuncsLib** -Projekt im **Projektmappen-Explorer**, und wählen Sie dann **Hinzufügen**, **Neues Element**aus. Wählen Sie im linken Bereich des Dialogfelds **Neues Element hinzufügen** unter **Visual C++** die Option **Code**aus. Wählen Sie im mittleren Bereich die Option **Headerdatei (.h)**. Geben Sie einen Namen für die Header-Datei – z. B. *MathFuncsLib.h*, und wählen Sie dann die **hinzufügen** Schaltfläche. Eine leere Headerdatei wird angezeigt.

2. Fügen Sie eine Klasse, die mit dem Namen `MyMathFuncs` zu geläufigen mathematischen Operationen wie Addition, Subtraktion, Multiplikation und Division. Der Code sollte diesem ähneln:

   [!code-cpp[NVC_Walkthrough_Create_Static_Lib#100](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_1.h)]

3. Zum Erstellen einer Quelldatei für die neue Klasse öffnen Sie das Kontextmenü für das **MathFuncsLib** -Projekt im **Projektmappen-Explorer**, und wählen Sie dann **Hinzufügen**, **Neues Element**aus. Wählen Sie im linken Bereich des Dialogfelds **Neues Element hinzufügen** unter **Visual C++** die Option **Code**aus. Wählen Sie im mittleren Bereich die Option **C++-Datei (.cpp)**. Geben Sie einen Namen für die Quelldatei, z. B. *MathFuncsLib.cpp*, und wählen Sie dann die **hinzufügen** Schaltfläche. Eine leere Quelldatei wird angezeigt.

4. Verwenden Sie diese Quelldatei zum Implementieren der Funktionalität von **MyMathFuncs**. Der Code sollte diesem ähneln:

   [!code-cpp[NVC_Walkthrough_Create_Static_Lib#110](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_2.cpp)]

5. Kompilieren Sie die statische Bibliothek dazu **erstellen** > **Projektmappe** in der Menüleiste. Dadurch wird eine statische Bibliothek erstellt, die in anderen Programmen verwendet werden kann.

   > [!NOTE]
   > Beim Erstellen über die Befehlszeile von Visual Studio müssen Sie das Programm in zwei Schritten erstellen. Führen Sie zunächst `cl /c /EHsc MathFuncsLib.cpp` zum Kompilieren des Codes und Erstellen einer Objektdatei mit dem Namen `MathFuncsLib.obj`. (Mit dem `cl`-Befehl wird der Compiler, "Cl.exe", aufgerufen, und mit der `/c`-Option wird Kompilieren ohne zu verknüpfen angegeben. Weitere Informationen finden Sie unter [/c (Kompilieren ohne Verknüpfen)](../build/reference/c-compile-without-linking.md).) Führen Sie `lib MathFuncsLib.obj` zum Verknüpfen des Codes und Erstellen der statischen Bibliothek `MathFuncsLib.lib`. (Mit dem `lib` Befehl wird der Bibliotheks-Manager, "Lib.exe", aufgerufen. Weitere Informationen finden Sie unter [LIB Reference](../build/reference/lib-reference.md).)

##  <a name="CreateAppToRefTheLib"></a> Erstellen eine C++-Konsolen-app, die auf die statische Bibliothek verweist.

### <a name="to-create-a-c-console-app-that-references-the-static-library"></a>So erstellen Sie eine Konsolenanwendung in C++, die auf die statische Bibliothek verweist

1. Klicken Sie in der Menüleiste auf **Datei** > **Neu** > **Projekt**.

2. Im linken Bereich die **neues Projekt** Dialogfeld erweitern Sie **installiert, Visual C++**, und wählen Sie dann **Windows Desktop**.

3. Wählen Sie im mittleren Bereich **-Assistenten für Windows Desktop**.

4. Geben Sie einen Namen für das Projekt, z. B. *MyExecRefsLib*– in der **Namen** Feld. Wählen Sie in der Dropdownliste neben **Projektmappe**die Option **Hinzufügen**aus. Dadurch wird das neue Projekt in die Projektmappe eingefügt, in der auch die statische Bibliothek enthalten ist. Klicken Sie auf die Schaltfläche **OK** .
5. Klicken Sie unter **Anwendungstyp**Option **Konsolenanwendung (.exe)**.

6. Klicken Sie unter **zusätzliche Optionen**, deaktivieren Sie die **vorkompilierter Header** Kontrollkästchen.

7. Wählen Sie **OK** zum Erstellen des Projekts.

##  <a name="UseLibInApp"></a> Verwenden der Funktionalität der statischen Bibliothek in der app

### <a name="to-use-the-functionality-from-the-static-library-in-the-app"></a>So verwenden Sie die Funktionalität der statischen Bibliothek in der App

1. Nach dem Erstellen einer Konsolenanwendung wird ein leeres Programm für Sie erstellt. Die Quelldatei erhält denselben Namen, den Sie zuvor ausgewählt haben. In diesem Beispiel heißt es `MyExecRefsLib.cpp`.

2. Bevor Sie die mathematischen Routinen verwenden können, müssen Sie auf die erstellte statische Bibliothek verweisen. Zu diesem Zweck öffnen Sie das Kontextmenü für die **MyExecRefsLib** Projekt **Projektmappen-Explorer**, und wählen Sie dann **hinzufügen** > **Verweis**.

3. Im Dialogfeld **Verweis hinzufügen** werden Bibliotheken aufgeführt, auf die Sie verweisen können. Auf der Registerkarte **Projekte** werden alle Projekte in der aktuellen Projektmappe und darin enthaltenen Bibliotheken aufgelistet. Aktivieren Sie auf der Registerkarte **Projekte** das Kontrollkästchen **MathFuncsLib** aus, und wählen Sie dann die Schaltfläche **OK** aus.

4. Verweis der `MathFuncsLib.h` -Headerdatei müssen Sie den enthaltenen Verzeichnispfad ändern. Erweitern Sie im Dialogfeld **Eigenschaftenseiten** von **MyExecRefsLib**den Knoten **Konfigurationseigenschaften** , erweitern Sie den Knoten **C/C++** , und wählen Sie dann **Allgemein**aus. Geben Sie neben **Zusätzliche Includeverzeichnisse**den Pfad des **MathFuncsLib** -Verzeichnisses ein, oder suchen Sie danach.

   Um nach dem Verzeichnispfad zu suchen, öffnen Sie die Dropdownliste für Eigenschaftswerte, und wählen Sie dann **Bearbeiten**aus. In der **Additional Include Directories** Dialogfeld, in das Textfeld ein, wählen Sie eine leere Zeile, und wählen Sie dann die Schaltfläche mit den Auslassungspunkten (**...** ) am Ende der Zeile. Wählen Sie im Dialogfeld **Verzeichnis auswählen** das **MathFuncsLib** -Verzeichnis aus, und wählen Sie dann die **Ordner auswählen** -Schaltfläche aus, um die Auswahl zu speichern und das Dialogfeld zu schließen. Wählen Sie im Dialogfeld **Zusätzliche Includeverzeichnisse** die Schaltfläche **OK** aus, und wählen Sie dann im Dialogfeld **Eigenschaftenseiten** die Schaltfläche **OK** aus, um die Änderungen am Projekt zu speichern.

5. Sie können nun die `MyMathFuncs` Klasse in dieser app. Zu diesem Zweck ersetzen Sie den Inhalt der `MyExecRefsLib.cpp` durch den folgenden Code:

   [!code-cpp[NVC_Walkthrough_Create_Static_Lib#120](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_3.cpp)]

6. Erstellen Sie die ausführbare Datei durch Auswahl **erstellen** > **Projektmappe** in der Menüleiste.

##  <a name="RunApp"></a> Ausführen der app

### <a name="to-run-the-app"></a>So führen Sie die App aus

1. Stellen Sie sicher, dass **MyExecRefsLib** als Standardprojekt ausgewählt wurde. Öffnen Sie dazu das Kontextmenü von **MyExecRefsLib** im **Projektmappen-Explorer**, und wählen Sie anschließend **Als Startprojekt festlegen**aus.

2. Führen Sie das Projekt, in der Menüleiste wählen **Debuggen** > **Starten ohne Debugging**. Die Ausgabe sollte dieser Ausgabe ähneln:

    ```Output
    a + b = 106.4
    a - b = -91.6
    a * b = 732.6
    a / b = 0.0747475
    ```

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweise: Erstellen und Verwenden einer Dynamic Link Library (C++)](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)  
[Desktopanwendungen (Visual C++)](../windows/desktop-applications-visual-cpp.md)