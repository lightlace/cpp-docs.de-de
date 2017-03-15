---
title: "Exemplarische Vorgehensweise: Erstellen eines Win32-Konsolenprogramms (C++)"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "get-started-article"
f1_keywords: 
  - "vcfirstapp"
  - "vccreatefirst"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Befehlszeilenanwendung [C++], Standard"
  - "Standardanwendungen [C++]"
ms.assetid: 48217e35-d892-46b7-93e3-f6f0b7e2da35
caps.latest.revision: 36
caps.handback.revision: "36"
ms.author: "mblome"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Erstellen eines Win32-Konsolenprogramms (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit Visual C\+\+ können in der integrierten Entwicklungsumgebung \(IDE\) von Visual Studio standardmäßige C\+\+\-Programme erstellt werden.  Durch Ausführen der Schritte in dieser exemplarischen Vorgehensweise können Sie ein Projekt erstellen, dem Projekt eine neue Datei hinzufügen, die Datei bearbeiten, um C\+\+\-Code hinzuzufügen und das Programm anschließend mithilfe von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] kompilieren und ausführen.  
  
 Sie können ein eigenes C\+\+\-Programm eingeben oder eines der Beispielprogramme verwenden.  Das Beispielprogramm in dieser exemplarischen Vorgehensweise ist eine Konsolenanwendung.  Von der Anwendung wird der `set`\-Container in der Standardvorlagenbibliothek \(STL\) verwendet.  
  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] entspricht dem 2003 C\+\+\-Standard, wobei folgende wichtige Ausnahmen zu berücksichtigen sind: zweistufige Namenssuche, Ausnahmespezifikationen und Export.  Darüber hinaus unterstützt [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] mehrere C\+\+0x\-Funktionen, z. B. Lambdas, Auto, static\_assert, rvalue\-Verweise und externe Vorlagen.  
  
> [!NOTE]
>  Wenn Kompatibilität mit dem Standard erforderlich ist, verwenden Sie die **\/Za**\-Compileroption, um Microsoft\-Erweiterungen für den Standard zu deaktivieren.  Weitere Informationen finden Sie unter [\/Za, \/Ze \(Spracherweiterungen deaktivieren\)](../build/reference/za-ze-disable-language-extensions.md).  
  
## Vorbereitungsmaßnahmen  
 Zur Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Grundkenntnisse in C\+\+.  
  
### So erstellen Sie ein neues Projekt und fügen eine Quelldatei hinzu  
  
1.  Erstellen Sie ein Projekt, indem Sie im Menü **Datei** auf **Neu** zeigen und anschließend auf **Projekt** klicken.  
  
2.  Klicken Sie im Projekttypenbereich von **Visual C\+\+** auf **Win32**, und klicken Sie dann auf **Win32\-Konsolenanwendung**.  
  
3.  Geben Sie einen Namen für das Projekt ein.  
  
     Standardmäßig erhält die Lösung, in der das Projekt enthalten ist, den gleichen Namen wie das Projekt. Sie können jedoch auch einen anderen Namen eingeben.  Sie können auch einen anderen Speicherort für das Projekt eingeben.  
  
     Klicken Sie auf **OK**, um das Projekt zu erstellen.  
  
4.  Klicken Sie im **Win32\-Anwendungs\-Assistenten** auf **Weiter**, wählen Sie **Leeres Projekt** aus,und klicken Sie anschließend auf **Fertig stellen**.  
  
5.  Klicken Sie im Menü **Ansicht** auf **Projektmappen\-Explorer**, wenn der **Projektmappen\-Explorer** nicht bereits geöffnet ist.  
  
6.  Fügen Sie dem Projekt folgendermaßen eine neue Quelldatei hinzu:  
  
    1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Ordner **Quelldateien**, zeigen Sie auf **Hinzufügen**, und wählen Sie anschließend **Neues Element** aus.  
  
    2.  Klicken Sie im Knoten **Code** auf **C\+\+\-Datei \(.cpp\)**, geben Sie einen Namen für die Datei ein, und klicken Sie anschließend auf **Hinzufügen**.  
  
     Die CPP\-Datei wird im Quelldateiordner im **Projektmappen\-Explorer** angezeigt, und die Datei wird im Visual Studio\-Editor geöffnet.  
  
7.  Geben Sie in der Datei im Editor ein gültiges C\+\+\-Programm ein, von dem die C\+\+\-Standardbibliothek verwendet wird, oder kopieren Sie eines der Beispielprogramme, und fügen Sie es in die Datei ein.  
  
     Sie können z. B. das [set::find](../misc/set-find-stl-samples.md)\-Beispielprogramm verwenden, bei dem es sich um eines der Beispiele für standardmäßige Vorlagenbibliotheken handelt, die in der Hilfe enthalten sind.  
  
     Wenn Sie das Beispielprogramm verwenden, beachten Sie die `using namespace std;`\-Direktive.  Diese Direktive ermöglicht dem Programm die Verwendung von `cout` und `endl`, ohne dass voll qualifizierte Namen \(`std::cout` und `std::endl`\) erforderlich sind.  
  
8.  Speichern Sie die Datei.  
  
9. Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
     Im **Ausgabefenster** werden Informationen zum Kompilierungsprozess angezeigt, z. B. der Speicherort des Buildprotokolls und eine Meldung über den Buildstatus.  
  
10. Klicken Sie im Menü **Debuggen** auf **Starten ohne Debuggen**.  
  
     Wenn Sie das Beispielprogramm verwendet haben, wird ein Befehlsfenster angezeigt. Dieses gibt an, ob bestimmte ganze Zahlen im Set enthalten sind.  
  
## Nächste Schritte  
 **Vorheriges Thema:** [Creating Command\-Line Applications \(C\+\+\)](assetId:///2505d9ed-aca4-426a-9071-078a2d707254).  **Nächstes Thema:** [Exemplarische Vorgehensweise: Kompilieren eines systemeigenen C\+\+\-Programms in der Befehlszeile](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md).  
  
## Siehe auch  
 [Visual C\+\+ Guided Tour](assetId:///499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [C\+\+\-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [C\+\+\-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)