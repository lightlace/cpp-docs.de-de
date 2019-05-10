---
title: Kompilieren von C++ / CLI-Programm, das die CLR
description: Verwenden Sie Microsoft C++ zum Erstellen von Programmen und Bibliotheken, die eine Verbindung herstellen können native C++ Code und .NET-Programme.
ms.date: 04/23/2019
helpviewer_keywords:
- command-line applications [C++], managed code
- compiling programs [C++]
- Visual C++, managed code
- managed code [C++]
ms.assetid: 339f89df-a5d2-4040-831a-ddbe25b5dce4
ms.openlocfilehash: 8462b2b031bdcdebf65d58974c521d80e57d856d
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221810"
---
# <a name="walkthrough-compile-a-ccli-program-that-targets-the-clr-in-visual-studio"></a>Exemplarische Vorgehensweise: Kompilieren von C++ / CLI-Programm, das die CLR in Visual Studio

Mithilfe von C++/CLI, die Sie erstellen C++ Programme, die Klassen von .NET als auch Native verwenden C++ Typen. C++/ CLI für die Verwendung in konsolenanwendungen und DLLs, die native umschließen soll C++ code ein, und es in .NET Programme zugänglich zu machen. Verwenden Sie zum Erstellen einer Windows-Benutzeroberfläche, die basierend auf .NET C# oder Visual Basic. 

Für dieses Verfahren können Sie ein eigenes C++-Programm eingeben oder eines der Beispielprogramme verwenden. Das Beispielprogramm, das für diese Vorgehensweise verwendet wird, erstellt eine Textdatei namens „textfile.txt“, die im Projektverzeichnis gespeichert wird.

## <a name="prerequisites"></a>Vorraussetzungen

- Grundlegende Kenntnisse der Programmiersprache C++.
- In Visual Studio 2017 und höher C++/CLI-Unterstützung ist eine optionale Komponente. Öffnen Sie zum Installieren der **Visual Studio-Installer** über das Windows-Startmenü. Stellen Sie sicher, dass die **Desktop-Entwicklung mit C++**  Kachel aktiviert ist, und klicken Sie in der **Optional** Abschnitt Komponenten, auch Kontrollkästchen  **C++CLI-Unterstützung**.

## <a name="create-a-new-project"></a>Erstellt ein neues Projekt

Die folgenden Schritte hängen davon ab, welche Version von Visual Studio Sie verwenden. Stellen Sie sicher, dass die Auswahl für die Version in der oberen linken Rand dieser Seite richtig festgelegt ist.

::: moniker range="vs-2019"

### <a name="to-create-a-ccli-project-in-visual-studio-2019"></a>Zum Erstellen einer C++/CLI-Projekt in Visual Studio-2019

1. In **Projektmappen-Explorer**, mit der rechten Maustaste oben zum Öffnen der **Erstellen eines neuen Projekts** Dialogfeld.

1. Geben Sie am oberen Rand des Dialogfelds, **CLR** in die Suche ein, und wählen Sie dann **leeres CLR-Projekt** in der Ergebnisliste aus. 

1. Wählen Sie die **erstellen** klicken, um das Projekt zu erstellen.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-ccli-project-in-visual-studio-2017"></a>Zum Erstellen einer C++/CLI-Projekt in Visual Studio 2017

1. Erstellen Sie ein neues Projekt. Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.

1. Klicken Sie in den Visual C++-Projekttypen auf **CLR**, und klicken Sie dann auf **leeres CLR-Projekt**.

1. Geben Sie einen Projektnamen ein. Standardmäßig erhält die Projektmappe, in der das Projekt enthalten ist, den gleichen Namen wie das neue Projekt. Sie können jedoch auch einen anderen Namen eingeben. Wenn Sie möchten, können Sie auch einen anderen Speicherort für das Projekt angeben.

1. Klicken Sie auf **OK**, um das neue Projekt zu erstellen.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-ccli-project-in-visual-studio-2015"></a>Zum Erstellen einer C++/CLI-Projekt in Visual Studio 2015

1. Erstellen Sie ein neues Projekt. Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.

1. Klicken Sie in den Visual C++-Projekttypen auf **CLR**, und klicken Sie dann auf **leeres CLR-Projekt**.

1. Geben Sie einen Projektnamen ein. Standardmäßig erhält die Projektmappe, in der das Projekt enthalten ist, den gleichen Namen wie das neue Projekt. Sie können jedoch auch einen anderen Namen eingeben. Wenn Sie möchten, können Sie auch einen anderen Speicherort für das Projekt angeben.

1. Klicken Sie auf **OK**, um das neue Projekt zu erstellen.

::: moniker-end

## <a name="add-a-source-file"></a>Fügen Sie eine Quelldatei hinzu

1. Wenn der **Projektmappen-Explorer** nicht angezeigt wird, klicken Sie im Menü **Ansicht** auf **Projektmappen-Explorer**.

1. Fügen Sie dem Projekt eine neue Quelldatei hinzu:

   - Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Ordner **Quelldateien**, zeigen Sie auf **Hinzufügen**, und klicken Sie dann auf **Neues Element**.

   - Klicken Sie auf **C++-Datei (.cpp)**, geben Sie einen Dateinamen ein, und klicken Sie dann auf **Hinzufügen**.

   Die **CPP**-Datei wird im Ordner **Quelldateien** im **Projektmappen-Explorer** angezeigt. Au0erdem wird ein Fenster im Registerkartenformat angezeigt, in dem Sie den Code eingeben können, den Sie in diese Datei einfügen möchten.

1. Klicken Sie in Visual Studio in die neu erstellte Registerkarte, und geben Sie ein gültiges Visual C++-Programm ein, oder kopieren Sie eines der Beispielprogramme und fügen es ein.

   Sie können z.B. das Beispielprogramm [How to: Write a Text File (C++/CLI) (Vorgehensweise: Schreiben einer Textdatei (C++/CLI))](how-to-write-a-text-file-cpp-cli.md) verwenden (im Knoten **File Handling and I/O (Dateibehandlung und E/A)** des Programmierhandbuchs).

   Beachten Sie, wenn Sie das Beispielprogramm verwenden, dass Sie das Schlüsselwort `gcnew` anstelle von `new` beim Erstellen eines .NET-Objekts verwenden, und dass `gcnew` ein Handle (`^`) anstelle eines Pointers (`*`) zurückgibt:

   `StreamWriter^ sw = gcnew StreamWriter(fileName);`

   Weitere Informationen zu C++/CLI-Syntax finden Sie unter [Komponentenerweiterungen für Laufzeitplattformen](../extensions/component-extensions-for-runtime-platforms.md).

1. Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.

   Im **Ausgabefenster** werden Informationen zum Kompilierungsprozess angezeigt, z.B. der Speicherort des Buildprotokolls und eine Meldung über den Buildstatus.

   Wenn Sie Änderungen vornehmen und das Programm ausführen, ohne einen Buildvorgang auszuführen, gibt ein Dialogfeld möglicherweise an, dass das Projekt nicht mehr aktuell ist. Aktivieren Sie in diesem Dialogfeld das Kontrollkästchen, bevor Sie auf **OK** klicken, wenn Sie möchten, dass Visual Studio immer die aktuellen Versionen von Dateien verwendet, anstatt Sie jedes zur Eingabe aufzufordern, wenn die Anwendung erstellt wird.

1. Klicken Sie im Menü **Debuggen** auf **Starten ohne Debuggen**.

1. Wenn Sie das Beispielprogramm verwendet haben und das Programm ausführen, wird ein Befehlsfenster angezeigt, das angibt, dass die Textdatei erstellt wurde.

   Die Textdatei **textfile.txt** befindet sich nun in Ihrem Projektverzeichnis. Sie können diese Datei mit dem Editor öffnen.

   > [!NOTE]
   > Durch Auswählen der leeren CLR-Projektvorlage wird automatisch die Compileroption `/clr` festgelegt. Klicken Sie zum Überprüfen mit der rechten Maustaste auf das Projekt im **Projektmappen-Explorer**, klicken Sie auf **Eigenschaften**, und überprüfen Sie dann die Option **Common Language Runtime-Unterstützung** im Knoten **Allgemein** der **Konfigurationseigenschaften**.

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[Projekte und Buildsysteme](../build/projects-and-build-systems-cpp.md)<br/>
