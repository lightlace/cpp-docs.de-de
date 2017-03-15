---
title: "Exemplarische Vorgehensweise: Kompilieren eines C++-Programms f&#252;r die CLR in Visual Studio"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Befehlszeilenanwendung [C++], Verwalteter Code"
  - "Kompilieren von Programmen [C++]"
  - "Verwalteter Code [C++]"
  - "Visual C++, Verwalteter Code"
ms.assetid: 339f89df-a5d2-4040-831a-ddbe25b5dce4
caps.latest.revision: 40
caps.handback.revision: "40"
ms.author: "corob"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Kompilieren eines C++-Programms f&#252;r die CLR in Visual Studio
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können Visual C\+\+\-Programme erstellen, die .NET\-Klassen verwenden, und diese Programme mithilfe der Entwicklungsumgebung von Visual Studio kompilieren.  
  
 Sie können für diesen Vorgang ein eigenes Visual C\+\+\-Programm eingeben oder eines der Beispielprogramme verwenden.  Das bei diesem Vorgang verwendete Beispielprogramm erstellt eine Textdatei mit dem Namen textfile.txt und speichert sie im Projektverzeichnis.  
  
## Vorbereitungsmaßnahmen  
 In diesen Themen wird davon ausgegangen, dass Sie die Grundlagen der Programmiersprache C\+\+ beherrschen.  
  
### So erstellen Sie in Visual Studio ein neues Projekt und fügen eine neue Quelldatei hinzu  
  
1.  Erstellen eines neuen Projekts  Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt...**.  
  
2.  Klicken Sie bei den Visual C\+\+\-Projekttypen auf **CLR**, und klicken Sie dann auf **Leeres CLR\-Projekt**.  
  
3.  Geben Sie einen Namen für das Projekt ein.  
  
     Standardmäßig erhält die Projektmappe, in der das Projekt enthalten ist, denselben Namen wie das neue Projekt. Sie können jedoch auch einen anderen Namen eingeben.  Wenn gewünscht, können Sie auch einen anderen Speicherort für das Projekt eingeben.  
  
     Klicken Sie auf **OK**, um das neue Projekt zu erstellen.  
  
4.  Wenn der Projektmappen\-Explorer nicht angezeigt wird, klicken Sie im Menü **Ansicht** auf **Projektmappen\-Explorer**.  
  
5.  Fügen Sie dem Projekt eine neue Quelldatei hinzu:  
  
    -   Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf den Ordner **Quelldateien**, zeigen Sie auf **Hinzufügen**, und klicken Sie auf **Neues Element**.  
  
    -   Klicken Sie auf **C\+\+\-Datei \(.cpp\)**, geben Sie einen Dateinamen ein, und klicken Sie dann auf **Hinzufügen**.  
  
     Die **.cpp**\-Datei wird im Ordner **Quelldateien** im Projektmappen\-Explorer angezeigt. Zusätzlich wird ein Fenster in Registerform angezeigt, das zur Eingabe des gewünschten Codes dient.  
  
6.  Klicken Sie in Visual Studio auf die neu erstellte Registerkarte, und geben Sie ein gültiges Visual C\+\+\-Programm ein, oder kopieren Sie eines der Beispielprogramme, und fügen Sie es ein.  
  
     Sie können z. B. das in [Gewusst wie: Schreiben einer Textdatei](../dotnet/how-to-write-a-text-file-cpp-cli.md) enthaltene Beispielprogramm verwenden \(im Knoten **Dateibehandlung und E\/A** des Programmierhandbuchs\).  
  
     Beachten Sie bei Verwendung des Beispielprogramms, das Sie beim Erstellen eines .NET\-Objekts anstelle von `new` das Schlüsselwort `gcnew` ``  verwenden und das `gcnew` anstelle eines Zeigers \(`*`\) ein Handle \(`^`\) zurückgibt:  
  
     `StreamWriter^ sw = gcnew StreamWriter(fileName);`  
  
     Weitere Informationen zur neuen Visual C\+\+\-Syntax finden Sie unter [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md).  
  
7.  Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
     Im **Ausgabefenster** werden Informationen zum Kompilierungsprozess angezeigt, z. B. der Speicherort des Buildprotokolls und eine Meldung über den Buildstatus.  
  
     Wenn Sie Änderungen vornehmen und das Programm ohne einen erneuten Buildvorgang ausführen, wird möglicherweise ein Dialogfeld angezeigt, das darauf hinweist, dass das Projekt nicht mehr aktuell ist.  Aktivieren Sie vor dem Klicken auf **OK** das Kontrollkästchen in diesem Dialogfeld, wenn Sie wünschen, dass Visual Studio zukünftig beim Erstellen der Anwendung immer die aktuellen Versionen der Dateien verwenden soll, anstatt Sie zur Eingabe aufzufordern.  
  
8.  Klicken Sie im Menü **Debuggen** auf **Starten ohne Debuggen**.  
  
9. Wenn Sie das Beispielprogramm verwendet haben, wird beim Ausführen des Programms ein Befehlsfenster angezeigt, das angibt, dass die Textdatei erstellt wurde.  Drücken Sie eine beliebige Taste, um das Befehlsfenster zu schließen.  
  
     Die Textdatei **textfile.txt** befindet sich jetzt im Projektverzeichnis.  Sie können diese Datei mit dem Editor öffnen.  
  
    > [!NOTE]
    >  Durch die Auswahl der Vorlage für ein leeres CLR\-Projekt wurde automatisch die Compileroption **\/clr** festgelegt.  Um dies zu überprüfen, klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Projekt. Klicken Sie dann auf **Eigenschaften**, und überprüfen Sie die Option **Common Language Runtime\-Unterstützung**, die sich im Knoten **Allgemein** der **Konfigurationseigenschaften** befindet.  
  
## Weitere Informationen  
 **Zurück:** [Exemplarische Vorgehensweise: Kompilieren eines systemeigenen C\+\+\-Programms in der Befehlszeile](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md) &#124; **Weiter:** [Exemplarische Vorgehensweise: Kompilieren eines C\-Programms in der Befehlszeile](../Topic/Walkthrough:%20Compiling%20a%20C%20Program%20on%20the%20Command%20Line.md)  
  
## Siehe auch  
 [Visual C\+\+ Guided Tour](assetId:///499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [C\+\+\-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [Erstellen von C\/C\+\+\-Programmen](../build/building-c-cpp-programs.md)