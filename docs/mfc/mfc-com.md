---
title: MFC-COM | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- MFC COM (MFC)
dev_langs:
- C++
helpviewer_keywords:
- MFC, COM support
- MFC ActiveX controls [MFC], COM support in MFC
- MFC COM [MFC]
- ActiveX controls [MFC], COM object model
- Active technology [MFC]
- COM [MFC], MFC support
ms.assetid: 7646bdcb-3a06-4ed5-9386-9b00f3979dcb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8257631e46a1ebcf5c882d9f87c628c04ccc84f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-com"></a>MFC COM
Eine Teilmenge von MFC dient zur Unterstützung von COM, während die meisten der Active Template Library (ATL) dient für die COM-Programmierung. Dieser Abschnitt beschreibt die MFC Unterstützung für COM.  
  
 Active Technology (z. B. ActiveX-Steuerelemente, Active Document-Container, OLE und So weiter) mit der Softwarekomponenten, die miteinander interagieren mit denen Sie waren, in einer vernetzten Umgebung, unabhängig von der Sprache ermöglichen das Component Object Model (COM) erstellt. Active Technology können verwendet werden, zum Erstellen von Anwendungen, die auf dem Desktop oder im Internet ausgeführt wird. Weitere Informationen finden Sie unter [Einführung in COM](../atl/introduction-to-com.md) oder [das Component Object Model](http://msdn.microsoft.com/library/windows/desktop/ms694363).  
  
 Aktive Technologien zählen Client- und Server-Technologien, darunter folgende:  
  
-   [Active Document-Container](../mfc/active-document-containment.md), in MFC-Versionen 4.2 unterstützt und können später erneut, Benutzer anzeigen [aktive Dokumente](../mfc/active-documents.md) (z. B. Microsoft Excel oder Word-Dateien), und aktivieren Sie die gesamte Schnittstelle des Dokuments systemeigenen in den gesamten Clientbereich der Anwendung ein [active Document-Container](../mfc/active-document-containers.md) wie Microsoft Office Binder oder Microsoft Internet Explorer. Die Container fungieren als Clients, während die Dokumente enthalten sind [aktive Dokumentserver](../mfc/active-document-servers.md). Weitere Informationen zur Verwendung von aktive Dokumente im Internet-Anwendungen finden Sie unter: [Active Documents für das Internet](../mfc/active-documents-on-the-internet.md).  
  
-   ActiveX-Steuerelemente sind interaktive Objekte, die in Containern, z. B. eine Website verwendet werden können. Weitere Informationen für ActiveX-Steuerelemente finden Sie unter:  
  
    -   [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)  
  
    -   [ActiveX-Steuerelemente für das Internet](../mfc/activex-controls-on-the-internet.md)  
  
    -   [Übersicht: Internet](../mfc/mfc-internet-programming-basics.md)  
  
    -   [Upgrade von einem vorhandenen ActiveX-Steuerelement auf das Internet verwendet werden](../mfc/upgrading-an-existing-activex-control.md)  
  
    -   [Debuggen von ActiveX-Steuerelement](/visualstudio/debugger/how-to-debug-an-activex-control)  
  
-   Active scripting steuert das integrierte Verhalten von einer oder mehrerer ActiveX-Steuerelemente in einem Browser oder Server. Weitere Informationen zu active scripting, finden Sie unter [Active Technology für das Internet](../mfc/active-technology-on-the-internet.md).  
  
-   [Automatisierung](../mfc/automation.md) (früher OLE-Automatisierung) ermöglicht es einer Anwendung in einer anderen Anwendung implementierten Objekte zu bearbeiten oder zu "Objekte verfügbar machen", damit sie bearbeitet werden können.  
  
     Das automatisierte Objekt kann lokal oder remote (auf einem anderen Computer, die über ein Netzwerk zugegriffen werden kann) sein. Automation ist für OLE und COM-Objekte verfügbar.  
  
-   Dieser Abschnitt enthält auch Informationen zum Schreiben von COM-Komponenten, die mithilfe von MFC, z. B. [Verbindungspunkte](../mfc/connection-points.md).  
  
 Eine Erläuterung der was OLE weiterhin aufgerufen wird, und was nun active-Technologie aufgerufen wird, finden Sie in den Themen zu [OLE](../mfc/ole-in-mfc.md).  
  
 Siehe auch Knowledge Base-Artikel Q248019: So wird's gemacht: zu verhindern, dass ausgelastet Dialogfeld Feld aus angezeigt werden während einer langwierigen com-Servervorgang.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Aktive Dokumente-Container](../mfc/active-document-containment.md)  
  
 [Automatisierung](../mfc/automation.md)  
  
 [Verbindungspunkte](../mfc/connection-points.md)  
  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../mfc/mfc-concepts.md)

