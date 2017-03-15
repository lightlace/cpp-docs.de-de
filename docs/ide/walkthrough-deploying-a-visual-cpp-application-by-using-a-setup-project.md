---
title: "Exemplarische Vorgehensweise: Bereitstellen einer Visual C++-Anwendung mithilfe eines Setup-Projekts"
ms.custom: na
ms.date: "12/16/2016"
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
  - "Bereitstellung für Visual C++"
ms.assetid: 66735cda-8fe3-4211-a19a-2cf717a12a3f
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Bereitstellen einer Visual C++-Anwendung mithilfe eines Setup-Projekts
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt, wie mit einem Setupprojekt eine Visual C\+\+\-Anwendung bereitgestellt wird.  
  
## Vorbereitungsmaßnahmen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   Einen Computer, auf dem [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] installiert ist  
  
-   Einen zusätzlichen Computer ohne die Visual C\+\+\-Bibliotheken  
  
### So stellen Sie eine Anwendung mithilfe eines Setupprojekts bereit  
  
1.  Verwenden Sie den **MFC\-Anwendungs**\-**Assistenten**, um eine neue Visual Studio\-Lösung zu erstellen.  Wenn Sie den Assistenten anzeigen möchten, erweitern Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C\+\+**, wählen Sie **MFC** und anschließend **MFC\-Anwendung** aus, geben Sie einen Namen für das Projekt ein, und klicken Sie anschließend auf **OK**.  
  
2.  Ändern Sie die aktive Lösungskonfiguration in **Release**.  Wählen Sie im Menü **Erstellen** die Option **Konfigurations\-Manager** aus.  Wählen Sie im Dialogfeld **Konfigurations\-Manager** im Dropdownfeld **Konfiguration der aktuellen Projektmappe** die Option **Release** aus.  
  
3.  Drücken Sie F7, um die Anwendung zu erstellen.  Sie können auch im Menü **Erstellen** auf **Projektmappe erstellen** klicken.  So kann das Setup\-Projekt, die Ausgabe dieses MFC\-Anwendungsprojekts zu verwenden.  
  
4.  Wenn Sie nicht bereits geschehen ist, Download InstallShield Limited\- Edition \(ISLE\), die für Visual Studio\-Entwickler frei ist und die Funktionalität der Projektvorlagen in Visual Studio für Setup und Bereitstellung ersetzt.  Wenn Sie mit dem Internet verbunden sind, öffnen Sie das Dialogfeld **Neues Projekt**, indem Sie **Datei**, **Neu**, **Projekt** auf der Menüleiste auswählen oder indem Sie auf die Projektmappe in **Projektmappen\-Explorer** mit der rechten Maustaste klicken und **Hinzufügen**, **Neues Projekt…** auswählen.  Erweitern Sie den Knoten **Andere Projekttypen**, wählen Sie **InstallShield Limited Edition aktivieren** im Knoten **Setup und Bereitstellung** aus, und befolgen Sie die Anweisungen, die angezeigt werden.  Sobald Sie heruntergeladen haben, werden und InstallShield Limited\- Edition aktiviert, schließen Sie Visual Studio und öffnen Sie es erneut.  
  
5.  Öffnen Sie das Dialogfeld erneut **Neues Projekt**, erweitern Sie den Knoten **Andere Projekttypen**, und wählen Sie **InstallShield Limited Edition\-Projekt** im Knoten **InstallShield Limited Edition** aus.  
  
6.  Folgen Sie den Anweisungen im Knoten **Erste Schritte** des Setup\-Projekts, das von der InstallShield Limited\- Editionsvorlage erstellt wird, um einen Ausgabeverweis dem Visual Studio\-MFC\-Projekt hinzuzufügen.  
  
7.  Erstellen Sie das Setupprojekt, die Installationsdatei \(setup.exe\) zu erstellen.  Hierzu, klicken Sie auf im den Setup\-Projekt\-Knoten in **Projektmappen\-Explorer** mit der rechten Maustaste und wählen Sie **Build** aus.  
  
     InstallShield Limited\- Edition erstellt die Setupdatei in der Setupprojektstruktur \(standardmäßig, ist sie möglicherweise im Unterordner Express\\SingleImage\\DiskImages\\DISK1 des Setup\-Projekts\).  
  
8.  Führen Sie das Setupprogramm auf einem zweiten Computer ausgeführt, der die Visual C\+\+\-Bibliotheken nicht vorhanden sind.  
  
## Siehe auch  
 [Bereitstellungsbeispiele](../ide/deployment-examples.md)