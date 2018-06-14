---
title: Kompilieren eines C++-Programms für die CLR | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- command-line applications [C++], managed code
- compiling programs [C++]
- Visual C++, managed code
- managed code [C++]
ms.assetid: 339f89df-a5d2-4040-831a-ddbe25b5dce4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2a7bcb0eead62730f0b70b0b1df64e5ed08f1f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33336094"
---
# <a name="walkthrough-compiling-a-c-program-that-targets-the-clr-in-visual-studio"></a>Exemplarische Vorgehensweise: Kompilieren eines C++-Programms für die CLR in Visual Studio
Sie können Visual C++-Programme erstellen, die .NET-Klassen verwenden, und diese kompilieren, indem Sie die Visual Studio-Entwicklungsumgebung verwenden.  
  
 Für diese Vorgehensweise können Sie Ihr eigenes Visual C++-Programm schreiben oder eines der Beispielprogramme verwenden. Das Beispielprogramm, das für diese Vorgehensweise verwendet wird, erstellt eine Textdatei namens „textfile.txt“, die im Projektverzeichnis gespeichert wird.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 In diesen Artikeln wird davon ausgegangen, dass Sie die Grundlagen der Programmiersprache C++ beherrschen.  
  
### <a name="to-create-a-new-project-in-visual-studio-and-add-a-new-source-file"></a>So erstellen Sie ein neues Projekt in Visual Studio und fügen eine neue Quelldatei hinzu  
  
1.  Erstellen Sie ein neues Projekt. Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.  
  
2.  Klicken Sie in den Visual C++-Projekttypen auf **CLR**, und klicken Sie dann auf **leeres CLR-Projekt**.  
  
3.  Geben Sie einen Projektnamen ein.  
  
     Standardmäßig erhält die Projektmappe, in der das Projekt enthalten ist, den gleichen Namen wie das neue Projekt. Sie können jedoch auch einen anderen Namen eingeben. Wenn Sie möchten, können Sie auch einen anderen Speicherort für das Projekt angeben.  
  
     Klicken Sie auf **OK**, um das neue Projekt zu erstellen.  
  
4.  Wenn der Projektmappen-Explorer nicht angezeigt wird, klicken Sie im Menü **Ansicht** auf **Projektmappen-Explorer**.  
  
5.  Fügen Sie dem Projekt eine neue Quelldatei hinzu:  
  
    -   Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf den Ordner **Quelldateien**, zeigen Sie auf **Hinzufügen**, und wählen Sie **Neues Element** aus.  
  
    -   Klicken Sie auf **C++-Datei (.cpp)**, geben Sie einen Dateinamen ein, und klicken Sie dann auf **Hinzufügen**.  
  
     Die **CPP**-Datei wird im Ordner **Quelldateien** im Projektmappen-Explorer angezeigt und ein Fenster im Registerkartenformat wird angezeigt, in dem Sie den Code eingeben, den Sie in diese Datei einfügen möchten.  
  
6.  Klicken Sie in Visual Studio in die neu erstellte Registerkarte, und geben Sie ein gültiges Visual C++-Programm ein, oder kopieren Sie eines der Beispielprogramme und fügen es ein.  
  
     Sie können beispielsweise das Beispielprogramm [How to: Write a Text File (C++/CLI) (Vorgehensweise: Schreiben einer Textdatei (C++/CLI))](../dotnet/how-to-write-a-text-file-cpp-cli.md) verwenden (im Knoten **Dateibehandlung und E/A** des Programmierhandbuchs).  
  
     Beachten Sie, wenn Sie das Beispielprogramm verwenden, dass Sie das Schlüsselwort `gcnew` anstelle von `new` beim Erstellen eines .NET-Objekts verwenden, und dass `gcnew` ein Handle (`^`) anstelle eines Pointers (`*`) zurückgibt:  
  
     `StreamWriter^ sw = gcnew StreamWriter(fileName);`  
  
     Weitere Informationen zur neuen Visual C++-Syntax finden Sie unter [Component Extensions for Runtime Platforms (Komponentenerweiterungen für Laufzeitplattformen)](../windows/component-extensions-for-runtime-platforms.md).  
  
7.  Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
     Im **Ausgabefenster** werden Informationen zum Kompilierungsprozess angezeigt, z.B. der Speicherort des Buildprotokolls und eine Meldung über den Buildstatus.  
  
     Wenn Sie Änderungen vornehmen und das Programm ausführen, ohne einen Buildvorgang auszuführen, gibt ein Dialogfeld möglicherweise an, dass das Projekt nicht mehr aktuell ist. Aktivieren Sie in diesem Dialogfeld das Kontrollkästchen, bevor Sie auf **OK** klicken, wenn Sie möchten, dass Visual Studio immer die aktuellen Versionen von Dateien verwendet, anstatt Sie jedes zur Eingabe aufzufordern, wenn die Anwendung erstellt wird.  
  
8.  Klicken Sie im Menü **Debuggen** auf **Starten ohne Debuggen**.  
  
9. Wenn Sie das Beispielprogramm verwendet haben und das Programm ausführen, wird ein Befehlsfenster angezeigt, das angibt, dass die Textdatei erstellt wurde. Drücken Sie eine beliebige Taste, um das Befehlsfenster zu schließen.  
  
     Die Textdatei **textfile.txt** befindet sich nun in Ihrem Projektverzeichnis. Sie können diese Datei mit dem Editor öffnen.  
  
    > [!NOTE]
    >  Durch Auswählen der leeren CLR-Projektvorlage wird automatisch die Compileroption **/clr** festgelegt. Klicken Sie zum Überprüfen mit der rechten Maustaste auf das Projekt im **Projektmappen-Explorer**, klicken Sie auf **Eigenschaften**, und überprüfen Sie dann die Option **Common Language Runtime-Unterstützung** im Knoten **Allgemein** der **Konfigurationseigenschaften**.  
  
## <a name="whats-next"></a>Weitere Informationen  
 **Zurück:** [Walkthrough: Compiling a Native C++ Program on the Command Line (Exemplarische Vorgehensweise: Kompilieren eines nativen C++-Programms über die Befehlszeile)](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md) &#124; **Weiter:**[Walkthrough: Compile a C Program on the Command Line (Exemplarische Vorgehensweise: Kompilieren eines C-Programms über die Befehlszeile)](../build/walkthrough-compile-a-c-program-on-the-command-line.md)  
  
## <a name="see-also"></a>Siehe auch  
 [C++ Language Reference (C++-Programmiersprachenreferenz)](../cpp/cpp-language-reference.md)   
 [Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)