---
title: "MFC COM"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "MFC COM (MFC)"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Active Technology [C++]"
  - "ActiveX-Steuerelemente [C++], COM-Objektmodell"
  - "COM [C++], MFC-Unterstützung"
  - "MFC [C++], COM-Unterstützung"
  - "MFC ActiveX-Steuerelemente [C++], COM-Unterstützung in MFC"
  - "MFC-COM [C++]"
ms.assetid: 7646bdcb-3a06-4ed5-9386-9b00f3979dcb
caps.latest.revision: 13
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# MFC COM
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Teilmenge MFC ist dafür konzipiert, die COM zu unterstützen, während die meisten Active Template Librarys \(ATL\) für COM\-Programmierung konzipiert ist.  Dieser Abschnitt beschreibt Themen MFC\-Unterstützung für COM.  
  
 Active Technologyen \(wie ActiveX\-Steuerelemente, Active Document\-Einschluss, OLE, usw.\). verwenden das Component Object Model \(COM\), um Softwarekomponenten zu aktivieren, um in einer vernetzten Umgebung, unabhängig von der Sprache miteinander interagieren, mit der sie erstellt wurden.  Active Technologyen können verwendet werden, um Anwendungen zu erstellen, die auf dem Desktop oder das Internet ausgeführt werden.  Weitere Informationen finden Sie unter [Einführung zu COM](../atl/introduction-to-com.md) oder [Mit dem Component Object Model](http://msdn.microsoft.com/library/windows/desktop/ms694363).  
  
 Active Technologyen enthalten Client\- und Servertechnologien, darunter die folgenden:  
  
-   [Active Document\-Einschluss](../mfc/active-document-containment.md) unterstützt, in MFC\-Versionen 4.2 und höher, können Benutzer, um den [Active Documents](../mfc/active-documents.md) aufzurufen \(wie Microsoft Excel oder Dateien abfassen\) und die ganze Schnittstelle der Ursprungsanwendung des Dokuments im gesamten Clientbereich von [Active Document\-Container](../mfc/active-document-containers.md) wie das Microsoft Office\-Binder oder Microsoft Internet Explorer zu aktivieren.  Die Container fungieren als Clients auf, während Dokumente die von der [Active Document\-Server](../mfc/active-document-servers.md) bereitgestellt werden.  Weitere Informationen zum Verwenden von aktiven Dokumenten in Internetanwendungen, finden Sie unter: [Active Documents im Internet](../mfc/active-documents-on-the-internet.md).  
  
-   ActiveX\-Steuerelemente sind interaktive Objekte, die in den Containern wie einer Website verwendet werden können.  Weitere Informationen zum ActiveX\-Steuerelement, finden Sie unter:  
  
    -   [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)  
  
    -   [ActiveX\-Steuerelemente im Internet](../mfc/activex-controls-on-the-internet.md)  
  
    -   [Übersicht: Internet](../mfc/mfc-internet-programming-basics.md)  
  
    -   [Aktualisieren Sie ein vorhandenes im Internet zu verwendenden ActiveX\-Steuerelement,](../mfc/upgrading-an-existing-activex-control.md)  
  
    -   [Debuggen eines ActiveX\-Steuerelements](../Topic/How%20to:%20Debug%20an%20ActiveX%20Control.md)  
  
-   Active Scripting steuert das integrierte Verhalten einer oder mehrerer ActiveX\-Steuerelemente von einem Browser oder von einem Server.  Weitere Informationen über Active Scripting, finden Sie unter [Active Technology im Internet](../mfc/active-technology-on-the-internet.md).  
  
-   [Automatisierung](../mfc/automation.md) \(früher bekannt als OLE\-Automatisierung\) ermöglicht es, dass eine Anwendung bearbeitet die Objekte, die in einer anderen Anwendung oder Objekte, sodass sie "verfügbar zu machen" implementiert werden, können bearbeitet werden.  
  
     Das automatisierte Objekt kann lokal oder [Remote\-](../mfc/remote-automation.md) \(auf einem anderen Computer aus zugreifen zu einem Netzwerk.\)  Automatisierung ist für OLE und COM\-Objekte verfügbar.  
  
-   Dieser Abschnitt enthält auch Informationen darüber, wie COM\-Komponenten mit MFC beispielsweise in unter [Verbindungspunkte](../mfc/connection-points.md).  
  
 Eine Erörterung, was noch OLE aufgerufen wird für, was jetzt aktive Technologie aufgerufen wird, finden Sie die Themen zu [OLE](../mfc/ole-in-mfc.md).  
  
 Außerdem finden Sie im Knowledge Base\-Artikel Q248019: HOWTO: Verhindern Sie, dass Server\-ausgelastetes Dialogfeld während eines längeren COM\-Vorgangs wird.  
  
## In diesem Abschnitt  
 [Active Document\-Einschluss](../mfc/active-document-containment.md)  
  
 [Automatisierung](../mfc/automation.md)  
  
 [Remote\- Automatisierung](../mfc/remote-automation.md)  
  
 [Verbindungspunkte](../mfc/connection-points.md)  
  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)  
  
## Siehe auch  
 [Konzepte](../mfc/mfc-concepts.md)