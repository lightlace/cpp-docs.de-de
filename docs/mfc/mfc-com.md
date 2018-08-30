---
title: MFC COM | Microsoft-Dokumentation
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
ms.openlocfilehash: 3e8c3af361e1ffb5928132727fa124f03a99e81e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43205648"
---
# <a name="mfc-com"></a>MFC COM
Eine Teilmenge von MFC dient zur Unterstützung von COM, während die meisten von der Active Template Library (ATL) dient für COM-Programmierung. Dieser Abschnitt der Themen befasst, MFC Unterstützung für COM.  
  
 Active Technologien (z. B. ActiveX-Steuerelemente, Active Document-Container, OLE und So weiter), die das Component Object Model (COM) verwenden, um Softwarekomponenten, die miteinander interagieren mit dem sie waren, in einer vernetzten Umgebung, unabhängig von der Sprache ermöglichen erstellt. Active Technology können verwendet werden, zum Erstellen von Anwendungen, die auf dem Desktop oder im Internet ausgeführt wird. Weitere Informationen finden Sie unter [Einführung in COM](../atl/introduction-to-com.md) oder [das Component Object Model](/windows/desktop/com/the-component-object-model).  
  
 Active Technology umfassen sowohl Client-als auch Technologien, einschließlich der folgenden:  
  
-   [Active Document-Container](../mfc/active-document-containment.md), unterstützt MFC-Version 4.2 und höher ermöglicht Benutzern das Anzeigen von [aktive Dokumente](../mfc/active-documents.md) (z. B. Microsoft Excel oder Word-Dateien), und aktivieren Sie die gesamte Schnittstelle des Dokuments systemeigenen in den gesamten Clientbereich der Anwendung ein [active Document-Container](../mfc/active-document-containers.md) z. B. Microsoft Office Binder oder Microsoft Internet Explorer. Die Container fungieren als Clients, während Dokumente von bereitgestellten [aktive Dokumentserver](../mfc/active-document-servers.md). Weitere Informationen zur Verwendung von aktive Dokumente in der Internet-Anwendungen finden Sie unter: [Active Documents für das Internet](../mfc/active-documents-on-the-internet.md).  
  
-   ActiveX-Steuerelemente sind interaktive Objekte, die in Containern, z. B. eine Website verwendet werden können. Weitere Informationen zu ActiveX-Steuerelementen finden Sie unter:  
  
    -   [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)  
  
    -   [ActiveX-Steuerelemente für das Internet](../mfc/activex-controls-on-the-internet.md)  
  
    -   [Übersicht: Internet](../mfc/mfc-internet-programming-basics.md)  
  
    -   [Aktualisieren eines vorhandenen ActiveX-Steuerelements auf das Internet verwendet werden](../mfc/upgrading-an-existing-activex-control.md)  
  
    -   [Debuggen von ActiveX-Steuerelement](/visualstudio/debugger/how-to-debug-an-activex-control)  
  
-   Active scripting steuert das integrierte Verhalten von ein oder mehrere ActiveX-Steuerelementen in einem Browser oder Server. Weitere Informationen zu active scripting, finden Sie unter [Active Technology für das Internet](../mfc/active-technology-on-the-internet.md).  
  
-   [Automation](../mfc/automation.md) (früher als OLE-Automatisierung) ermöglicht es einer Anwendung in einer anderen Anwendung implementierten Objekte zu bearbeiten oder "Objekte verfügbar zu machen", damit sie bearbeitet werden können.  
  
     Das automatisierte Objekt kann lokal oder remote (auf einem anderen Computer, die über ein Netzwerk zugegriffen werden kann) sein. Automation ist für OLE und COM-Objekte verfügbar.  
  
-   Dieser Abschnitt enthält auch Informationen zum Schreiben von COM-Komponenten, die mithilfe von MFC, z. B. [Verbindungspunkte](../mfc/connection-points.md).  
  
 Eine Erläuterung der zuerst immer noch eine so genannte OLE im Vergleich zu, die jetzt active-Technologie bezeichnet wird, finden Sie in den Themen zu [OLE](../mfc/ole-in-mfc.md).  
  
 Siehe auch die Knowledge Base-Artikel Q248019: So wird's gemacht: zu verhindern, dass Server ausgelastet Dialogfeld im aus angezeigt werden während einer langwierigen com-Vorgang.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Aktive Dokumente-Container](../mfc/active-document-containment.md)  
  
 [Automatisierung](../mfc/automation.md)  
  
 [Verbindungspunkte](../mfc/connection-points.md)  
  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../mfc/mfc-concepts.md)

