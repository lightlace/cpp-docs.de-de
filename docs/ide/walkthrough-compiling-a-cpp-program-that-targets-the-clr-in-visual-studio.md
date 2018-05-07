---
title: Kompilieren eines C++-Programms die CLR | Microsoft Docs
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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-compiling-a-c-program-that-targets-the-clr-in-visual-studio"></a>Exemplarische Vorgehensweise: Kompilieren eines C++-Programms für die CLR in Visual Studio
Sie können Visual C++-Programme erstellen, die Klassen von .NET verwenden, und kompilieren Sie diese mithilfe der Visual Studio-Entwicklungsumgebung.  
  
 Für dieses Verfahren können Sie Visual C++-Programm eingeben oder eines der Beispielprogramme verwenden. Das Beispielprogramm, das wir in diesem Verfahren verwenden, erstellt eine Textdatei mit dem Namen textfile.txt und speichert es in das Projektverzeichnis.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 In diesen Themen wird davon ausgegangen, dass Sie die Grundlagen der Programmiersprache C++ beherrschen.  
  
### <a name="to-create-a-new-project-in-visual-studio-and-add-a-new-source-file"></a>Zum Erstellen eines neuen Projekts in Visual Studio, und fügen Sie eine neue Quelldatei hinzu  
  
1.  Erstellen Sie ein neues Projekt. Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.  
  
2.  Klicken Sie in der Visual C++-Projekttypen auf **CLR**, und klicken Sie dann auf **leeres CLR-Projekt**.  
  
3.  Geben Sie einen Projektnamen ein.  
  
     Die Lösung, die das Projekt enthält, hat den gleichen Namen wie das neue Projekt standardmäßig, jedoch können Sie einen anderen Namen eingeben. Wenn Sie möchten, können Sie einen anderen Speicherort für das Projekt eingeben.  
  
     Klicken Sie auf **OK** zum Erstellen eines neuen Projekts.  
  
4.  Wenn der Projektmappen-Explorer nicht sichtbar ist, klicken Sie auf **Projektmappen-Explorer** auf die **Ansicht** Menü.  
  
5.  Fügen Sie dem Projekt eine neue Quelldatei hinzu:  
  
    -   Mit der rechten Maustaste die **Quelldateien** Ordner zeigen Sie im Projektmappen-Explorer auf **hinzufügen** , und klicken Sie auf **neues Element**.  
  
    -   Klicken Sie auf **C++-Datei (.cpp)** und geben Sie einen Dateinamen ein, und klicken Sie dann auf **hinzufügen**.  
  
     Der **cpp** Datei erscheint der **Quelldateien** Ordner im Projektmappen-Explorer und in einem Fenster im Registerkartenformat angezeigt wird, geben Sie den Code ein in dieser Datei werden sollen.  
  
6.  Klicken Sie in der neu erstellte Registerkarte in Visual Studio, und geben Sie ein gültiges Visual C++-Programm oder kopieren Sie eines der Beispielprogramme.  
  
     Beispielsweise können Sie der [wie: Schreiben einer Textdatei (C + c++ / CLI)](../dotnet/how-to-write-a-text-file-cpp-cli.md) Beispielprogramm (in der **Dateibehandlung und e/a-** Knoten die Programmierhandbuch).  
  
     Wenn Sie das Beispielprogramm verwenden, beachten Sie, dass Sie verwenden die `gcnew` -Schlüsselwort anstelle von `new` beim Erstellen des Objekts, und dass `gcnew` gibt ein Handle zurück (`^`) anstelle eines Zeigers (`*`):  
  
     `StreamWriter^ sw = gcnew StreamWriter(fileName);`  
  
     Weitere Informationen zur neuen Visual C++-Syntax finden Sie unter [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md).  
  
7.  Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
     Die **Ausgabe** Fenster werden Informationen zum Kompilierungsprozess angezeigt, wie den Speicherort des Buildprotokolls und eine Meldung, die den Buildstatus angezeigt.  
  
     Wenn Sie Änderungen vornehmen, und führen Sie das Programm ohne einen Build auszuführen, ein Dialogfeld wird angegeben, dass das Projekt nicht mehr aktuell ist. Aktivieren Sie das Kontrollkästchen in diesem Dialogfeld aus, bevor Sie auf **OK** ggf. Visual Studio immer die aktuellen Versionen von Dateien verwenden, anstatt Sie jedes Mal beim Erstellen der Anwendung.  
  
8.  Auf der **Debuggen** Menü klicken Sie auf **Starten ohne Debugging**.  
  
9. Wenn Sie das Beispielprogramm verwendet, wenn Sie das Programm ausführen, wird ein Befehlsfenster angezeigt, der angibt, dass die Textdatei erstellt wurde. Drücken Sie eine beliebige Taste, um das Befehlsfenster zu schließen.  
  
     Die **textfile.txt** Textdatei befindet sich jetzt im Projektverzeichnis. Sie können diese Datei mithilfe des Editors öffnen.  
  
    > [!NOTE]
    >  Wählen die leere CLR-Projektvorlage automatisch festgelegt die **"/ CLR"** -Compileroption. Um dies zu überprüfen, Maustaste das Projekt im **Projektmappen-Explorer** und auf **Eigenschaften**, und überprüfen Sie dann die **Common Language Runtime-Unterstützung** -Option in der  **Allgemeine** Knoten **Konfigurationseigenschaften**.  
  
## <a name="whats-next"></a>Weitere Informationen  
 **Vorherige:** [Exemplarische Vorgehensweise: Kompilieren eines systemeigenen C++-Programms in der Befehlszeile](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md) &#124; **weiter:**[Exemplarische Vorgehensweise: Kompilieren ein C-Programms in der Befehlszeile](../build/walkthrough-compile-a-c-program-on-the-command-line.md)  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)