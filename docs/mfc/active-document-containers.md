---
title: Active Document-Container | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- active documents [MFC], containers
- active document containers [MFC]
- containers [MFC], active document
- MFC COM, active document containment
ms.assetid: ba20183a-8b4c-440f-9031-e5fcc41d391b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3c912b6c703ef7e05825e070d09f0a1b3cd73003
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932158"
---
# <a name="active-document-containers"></a>Active Document-Container
Active Document-Container, z. B. Microsoft Office Binder oder Internet Explorer ermöglicht Ihnen, arbeiten mit anderen Anwendungstypen in einem einzelnen Frame (statt Sie zu erstellen und verwenden mehrere Frames der Anwendung für die einzelnen zwingen, mehrere Dokumente Dokumenttyp).  
  
 MFC bietet vollständige Unterstützung für active Document-Container in der `COleDocObjectItem` Klasse. Können Sie den MFC-Anwendung-Assistenten erstellen Sie einen active Document-Container durch Auswahl der **Active Document-Container** Kontrollkästchen auf der **Verbunddokumente** Seite des Assistenten für die MFC-Anwendung. Weitere Informationen finden Sie unter [Erstellen einer Containeranwendung für aktive Dokumente](../mfc/creating-an-active-document-container-application.md).  
  
 Weitere Informationen zu active Document-Container finden Sie unter:  
  
-   [Anforderungen von Containern](#container_requirements)  
  
-   [Website-Dokumentobjekte](#document_site_objects)  
  
-   [Standortobjekte anzeigen](#view_site_objects)  
  
-   [Rahmenobjekt](#frame_object)  
  
-   [Verschachteln des Hilfemenüs](../mfc/help-menu-merging.md)  
  
-   [Programmgesteuertes Drucken](../mfc/programmatic-printing.md)  
  
-   [Befehlsziele](../mfc/message-handling-and-command-targets.md)  
  
##  <a name="container_requirements"></a> Anforderungen von Containern  
 Active Document-Unterstützung für active Document-Container bedeutet mehr als nur schnittstellenimplementierungen: Es sind auch Kenntnisse über die Schnittstellen des enthaltenen Objekts. Das gleiche gilt für active Document-Erweiterungen, in dem der Container auch diese Schnittstellen für die aktive Dokumente selbst verwenden wissen, wie Sie muss.  
  
 Active Document-Container, der aktive Dokumente integrieren müssen:  
  
-   Behandeln von Objektspeicher über in der Lage sein der `IPersistStorage` -Schnittstelle, d. h. es muss bereitstellen eine `IStorage` Instanz für jede aktive Dokument.  
  
-   Unterstützt die grundlegenden Einbetten von Funktionen von OLE-Dokumenten ""-Standortobjekte (einer pro-Dokument oder einbetten) implementiert, `IOleClientSite` und `IAdviseSink`.  
  
-   Direkte Aktivierung von eingebetteten Objekten oder aktive Dokumente zu unterstützen. Der Container Standortobjekte implementieren müssen `IOleInPlaceSite` rahmenobjekt des Containers bereitstellen muss `IOleInPlaceFrame`.  
  
-   Die aktive Dokumente Erweiterungen durch Implementierung unterstützen `IOleDocumentSite` auf den Mechanismus für den Container zum Kommunizieren mit dem Dokument verwendet. Optional kann der Container active Document-Schnittstellen implementieren `IOleCommandTarget` und `IContinueCallback` zum Abholen einfache Befehle wie das Drucken oder speichern.  
  
 Die Frameobjekt, das Anzeigen von Objekten und das Containerobjekt können optional implementieren `IOleCommandTarget` zur Unterstützung der Verteilungs bestimmte Befehle, wie in beschrieben [Befehlsziele](../mfc/message-handling-and-command-targets.md). Anzeigen und Containerobjekte können optional auch implementieren `IPrint` und `IContinueCallback`, zum Programmgesteuertes Drucken, zu unterstützen, wie in beschrieben [programmgesteuerten Drucken](../mfc/programmatic-printing.md).  
  
 Die folgende Abbildung zeigt die konzeptionelle Beziehung zwischen einem Container und seinen Komponenten (links), und das aktive Dokument und seinen Ansichten (rechts). Das aktive Dokument verwaltet, Speicher und Daten, und die Ansicht zeigt oder gibt optional die Daten. Schnittstellen in Fettdruck sind diejenigen, die für die Teilnahme des aktiven Dokuments erforderlich; Die fett und kursiv sind optional. Alle anderen Schnittstellen sind erforderlich.  
  
 ![Active Document-Container-Schnittstellen](../mfc/media/vc37gj1.gif "vc37gj1")  
  
 Ein Dokument, das nur eine einzige Ansicht unterstützt, kann die Ansicht und den Dokument-Komponenten (d. h. die entsprechenden Schnittstellen) für eine einzelnes konkrete Klasse implementieren. Darüber hinaus kann ein Container-Standort, der eine zu einem gegebenen Zeitpunkt nur unterstützt das Dokument und der Website anzeigen in einer einzelnen konkrete Standort-Klasse kombinieren. Rahmenobjekt des Containers, muss jedoch unterschiedliche bleiben und Komponente für den Container ist lediglich hier enthalten, um ein vollständiges Bild der Architektur erteilen; Es wird nicht von der Architektur des active Document Containment beeinflusst.  
  
##  <a name="document_site_objects"></a> Website-Dokumentobjekte  
 In der active Document Containment-Architektur eine Website entspricht einer Client-Standortobjekt im OLE-Dokumente durch das Hinzufügen der `IOleDocument` Schnittstelle:  
  
 `interface IOleDocumentSite : IUnknown`  
  
 `{`  
  
 `HRESULT ActivateMe(IOleDocumentView *pViewToActivate);`  
  
 `}`  
  
 Die Website ist im Grunde den Container für eine oder mehrere "Ansicht" Standortobjekte. Jedes Sichtobjekt für den Standort bezieht sich auf einzelne Sichtobjekte des Dokuments von der Website verwaltet werden. Wenn der Container nur eine einzige Ansicht pro Website im Dokument unterstützt, kann sie das Dokument und dem Standort Ansicht mit einer einzigen konkreten Klasse implementieren.  
  
##  <a name="view_site_objects"></a> Standortobjekte anzeigen  
 Standortobjekt für einen Container Ansicht verwaltet den Anzeigebereich für eine bestimmte Ansicht eines Dokuments. Zusätzlich zur Unterstützung des Standards `IOleInPlaceSite` Schnittstelle View-Website auch in der Regel implementiert `IContinueCallback` für programmgesteuerte Kontrolle. (Beachten Sie, die das Ansichtsobjekt nie abfragt `IContinueCallback` so, dass sie tatsächlich implementiert werden kann, auf alle Objekte der Container Wünsche.)  
  
 Ein Container, der mehrere Ansichten unterstützt muss mehrere Ansichten Standortobjekte innerhalb der Website erstellen können. Dies bietet einer Ansicht jeweils mit separaten Aktivierung und Deaktivierung-Diensten, wie angegeben durch `IOleInPlaceSite`.  
  
##  <a name="frame_object"></a> Rahmenobjekt  
 Der Container-rahmenobjekt ist meistens, desselben Frames, die für die direkte Aktivierung in OLE-Dokumenten, d. h. verwendet wird, die Menü- und Symbolleistenelemente Aushandlung behandelt. Ein-Objekt hat Zugriff auf dieses Frameobjekt über `IOleInPlaceSite::GetWindowContext`, dem bietet außerdem Zugriff auf die Container-Objekt, das Containerdokument (auf der Symbolleiste auf Bereich-Aushandlung und die darin enthaltenen Objektenumeration verarbeiten kann) darstellt.  
  
 Active Document-Container kann Frames erweitern, indem Sie hinzufügen `IOleCommandTarget`. Dadurch kann er für Befehle zu empfangen, die in der Benutzeroberfläche für das aktive Dokument auf die gleiche Weise stammen, dass dieser Schnittstelle kann Container für die gleichen Befehle senden ermöglichen (z. B. **neue Datei**, **öffnen**,  **Speichern Sie als**, **Drucken**; **Kopie bearbeiten**, **einfügen**, **Rückgängig**, usw.) in einem aktiven Dokument. Weitere Informationen finden Sie unter [Befehlsziele](../mfc/message-handling-and-command-targets.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Aktive Dokumente-Container](../mfc/active-document-containment.md)

