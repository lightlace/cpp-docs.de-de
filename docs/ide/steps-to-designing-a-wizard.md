---
title: "Schritte zum Entwerfen eines Assistenten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Benutzerdefinierte Assistenten, Entwerfen"
ms.assetid: dc22746b-99e3-4569-a8b4-b3d7cbabf8f2
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Schritte zum Entwerfen eines Assistenten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mithilfe eines Assistenten können Sie allgemeine Projektstartdateien erstellen und konfigurieren.  Wie jedes Projekt muss auch das Erstellen eines Assistenten geplant werden.  Die folgenden Schritte beschreiben einen Weg, um sich mit dem benutzerdefinierten Visual C\+\+\-Assistenten vertraut zu machen und ihn in eigenen Projekten einzusetzen.  
  
1.  Sehen Sie sich die in Visual Studio enthaltenen [Beispiele für benutzerdefinierte Assistenten](assetId:///6afa2143-062c-4a68-81ca-66cbf4b95261) an.  
  
2.  Legen Sie die Grundlagen für den Projekttyp fest, der durch den Assistenten erstellt werden soll.  Wie bei der Erstellung aller anderen Anwendungen kann dieser Vorgang durch mehrere Hände gehen und mehrfach wiederholt werden.  
  
3.  Erstellen Sie das Projekt mit dem [benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md) von Visual C\+\+. Wählen Sie dabei Optionen für die Benutzeroberfläche und die Seitenanzahl aus.  
  
    > [!NOTE]
    >  Wenn Sie auf eine Benutzeroberfläche verzichten \(d. h., wenn Sie im benutzerdefinierten Assistenten unter [Anwendungseinstellungen, Benutzerdefinierter Assistent](../ide/application-settings-custom-wizard.md) die Option **Benutzeroberfläche** deaktivieren\), legt der Assistent den benutzerdefinierten Parameter WIZARD\_UI\=**FALSE** fest und erstellt Projektvorlagendateien ohne Benutzereingabe\- und HTM\-Dateien.  Demzufolge müssen Sie auch nicht die Anzahl der Seiten angeben.  Weitere Informationen finden Sie unter [VSZ\-Datei \(Projektsteuerung\)](../ide/dot-vsz-file-project-control.md).  
  
4.  [Untersuchen Sie das grundlegende Projekt](../ide/examining-the-basic-wizard-project.md), das vom benutzerdefinierten Assistenten erstellt wurde.  
  
5.  Wenn der Assistent eine Benutzeroberfläche besitzt, führen Sie ihn aus, um [mehr über die Mechanismen des benutzerdefinierten Assistenten zu erfahren](../ide/examining-the-mechanics-of-a-wizard.md).  
  
6.  [Passen Sie den grundlegenden Assistenten an](../ide/customizing-your-wizard.md).  
  
7.  [Fügen Sie kontextbezogene Hilfe hinzu](../ide/providing-context-sensitive-help.md).  
  
8.  [Stellen Sie eine Fehlerbehandlung](../ide/handling-errors-in-wizards.md) für JScript\- und HTML\-Code bereit.  
  
9. Erstellen und testen Sie den Assistenten.  
  
10. Debuggen Sie den Assistenten.  Weitere Informationen finden Sie unter [Debuggen von Skript\- und Webanwendungen](../Topic/Debugging%20Web%20Applications%20and%20Script.md).  
  
    > [!NOTE]
    >  Wenn Sie JScript debuggen, ist das Debuggen im gemischten Modus mit systemeigenem Code nicht möglich.  
  
## Siehe auch  
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Benutzerdefinierter Assistent](../ide/custom-wizard.md)   
 [Für den Assistenten erstellte Dateien](../ide/files-created-for-your-wizard.md)