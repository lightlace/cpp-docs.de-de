---
title: "Weiterverteilen von Steuerelementen | Microsoft Docs"
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
  - "ActiveX-Steuerelemente [C++], Neuverteilung"
  - "Weiterverteilbare Steuerelemente"
ms.assetid: 32d03b95-d328-4f10-ad9b-f3ebbe03339d
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Weiterverteilen von Steuerelementen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit Visual C\+\+ .NET stehen Ihnen ActiveX\-Steuerelemente für Anwendungen zur Verfügung. Die Steuerelemente können zusammen mit den Anwendungen weiterverteilt werden. Im Dialogfeld **ActiveX\-Steuerelement einfügen** können Sie die OCX\- oder DLL\-Datei eines Steuerelements anzeigen, indem Sie es auswählen.  
  
 Eine Liste der verteilbaren, in Visual C\+\+ enthaltenen ActiveX\-Steuerelemente finden Sie in der Datei "Program Files\\Microsoft Visual Studio .NET 2003\\redist.txt" auf CD 2 der Produkt\-CD\-ROMs für Visual C\+\+ .NET. Alle im Ordner "Win\\System" enthaltenen OCX\-Dateien dürfen verteilt werden.  
  
 Unter [MFC\-ActiveX\-Steuerelemente: Weitergabe von ActiveX\-Steuerelementen](../../mfc/mfc-activex-controls-distributing-activex-controls.md) wird erläutert, wie verteilbare ActiveX\-Steuerelemente installiert und registriert werden.  
  
 Unter [Mergemodulprojekte](assetId:///e92e4f85-fba5-45ee-a432-892a956daeb9) erfahren Sie, wie die Verteilung von Dateien durch Mergemodule in Visual Studio .NET verwaltet wird.  
  
 Unter [Neuverteilen von Datenbankunterstützungsdateien](../../ide/redistributing-database-support-files.md) wird das Weiterverteilen von Unterstützungsdateien für die Datenbanktechnologien im Microsoft Data Access SDK.  
  
 Wenn Ihre Anwendung ein ActiveX\-Steuerelement mit einer Verbindung mit einer Datenbank verwendet, müssen Sie die folgenden Komponenten installieren bzw. die folgenden Schritte beachten:  
  
-   **DCOM für Windows.** Sie müssen „Dcom98.exe“ oder „Dcom95.exe“ auf jedem Computer ausführen, auf dem Windows\-Versionen ausgeführt werden, die älter als Windows 2000 sind. \(„Dcom98.exe“ ist speziell für Windows 98 konzipiert, während „Dcom95.exe“ speziell für Windows 95 bestimmt ist.\)  
  
-   **MDAC 2.8 SDK.** Das Microsoft Data Access 2.8 SDK sollte auf dem Zielcomputer installiert werden. Es kann unter [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=205525](http://go.microsoft.com/fwlink/?LinkId=205525) heruntergeladen werden.  
  
-   **MDAC 2.8\-Weitergabeprogramm.** Das MDAC 2.8 SDK wurde zur Verwendung mit dem MDAC 2.8\-Weitergabeprogramm \(MDAC\_TYP.EXE\) entworfen. MDAC\_TYP.EXE kann unter [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=164412](http://go.microsoft.com/fwlink/?LinkId=164412) heruntergeladen werden.  
  
-   **Replizieren des DSNs.** Darüber hinaus müssen Sie den Datenquellennamen auf dem Zielcomputer replizieren. Dieser Vorgang kann programmgesteuert mit Funktionen wie [ConfigDSN](https://msdn.microsoft.com/en-us/library/ms709275.aspx) ausgeführt werden.  
  
## Wichtige Hinweise zur Weitergabe von Komponenten  
  
-   **Weiterverteilen von DAO\-Komponenten** Microsoft empfiehlt die Verwendung von Jet 4.0 SP3 \(Version 2927.04\) oder höher. Jet 4.0 SP3 ist im Lieferumfang von Windows 2000 und Windows Me enthalten. Durch die Verwendung dieser Jet\-Version verringert sich die Anzahl der Jet\-Versionen, die mit Ihrer Anwendung getestet werden müssen.  
  
     Windows XP wird mit einer aktualisierten Version des Jet\-Service Packs geliefert, die in früheren Versionen von Windows nicht enthalten war. Beim Testen von Anwendungen unter Windows XP wird automatisch die in Windows XP enthaltene Jet\-Version verwendet. Daher müssen DAO\-Anwendungen vor der Veröffentlichung unter Verwendung beider Versionen von Jet 4.0 getestet werden.  
  
     Der einzige Unterschied besteht darin, dass Probleme, die seit der Freigabe von Windows 2000 ermittelt wurden, in der Windows XP\-Version korrigiert wurden. Falls die Benutzer Ihrer Anwendung keine Probleme vorfinden, besteht keine Notwendigkeit, über Jet 4.0 SP3 hinaus zu aktualisieren.  
  
-   **Bekannte Probleme mit ActiveX\-Steuerelementen:** Bei der dynamischen Erstellung von Instanzen verteilbarer ActiveX\-Steuerelemente auf Computern, auf denen Visual C\+\+ nicht installiert wurde, tritt ein bekanntes Problem auf. Siehe dazu den Knowledge Base\-Artikel „PRB: Fehler bei dynamischer Erstellung von verteilbaren Steuerelementen“ \(Q151804\). Knowledge Base\-Artikel finden Sie auf der MSDN Library\-CD\-ROM oder unter [http:\/\/support.microsoft.com](http://support.microsoft.com). Darüber hinaus tritt ein bekanntes Problem bei der Integration einiger ActiveX\-Steuerelemente in ein Dialogfeld auf. Sie erhalten ein Meldungsfeld mit dem Hinweis, dass das Steuerelement eine Entwurfslizenz erfordert. Siehe dazu den Knowledge Base\-Artikel "PRB: Entwurfslizenz für Microsoft ActiveX\-Steuerelemente erforderlich" \(Q155059\). Knowledge Base\-Artikel finden Sie auf der MSDN Library\-CD\-ROM oder unter [http:\/\/support.microsoft.com](http://support.microsoft.com).  
  
-   **Visual Studio\-lizenzierte Steuerelemente:** Visual Studio\-Lizenznehmer sind berechtigt, zusätzliche ActiveX\-Steuerelemente zu verteilen, die für andere Entwicklungstools von Visual Studio spezifisch sind. Beispielsweise wird das Diagrammsteuerelement mit Visual Basic ausgeliefert, das wiederum zum Lieferumfang von Visual Studio gehört. Wenn Sie daher Visual C\+\+ im Rahmen einer Visual Studio\-Lizenz verwenden, können Sie auch das Diagrammsteuerelement weiterverteilen. Haben Sie jedoch nur Visual C\+\+ erworben, sind Sie nicht berechtigt, das Steuerelement zu verteilen.  
  
## Siehe auch  
 [Verwenden von ActiveX\-Steuerelementen](../../data/ado-rdo/using-activex-controls.md)   
 [MFC\-ActiveX\-Steuerelemente: Verteilen von ActiveX\-Steuerelementen](../../mfc/mfc-activex-controls-distributing-activex-controls.md)