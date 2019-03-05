---
title: Active Document-Container
ms.date: 11/19/2018
helpviewer_keywords:
- active documents [MFC], containers
- active document containers [MFC]
- containers [MFC], active document
- MFC COM, active document containment
ms.assetid: ba20183a-8b4c-440f-9031-e5fcc41d391b
ms.openlocfilehash: 6e4defaf347f0d539ef023ee9c0e1e85dd2390db
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57288960"
---
# <a name="active-document-containers"></a>Active Document-Container

Active Document-Container, z. B. Microsoft Office Binder oder Internet Explorer ermöglicht Ihnen die Arbeit mit mehreren Dokumenten verschiedene Anwendungstypen in ein einzelnes Frame (anstatt zum Erstellen und verwenden mehrere Frames der Anwendung für die einzelnen Dokumenttyp).

MFC bietet vollständige Unterstützung für active Document-Container in der `COleDocObjectItem` Klasse. Können Sie den Assistenten zum MFC-Anwendungen erstellen Sie einen active Document-Container durch Auswählen der **Active Document-Container** auf das Kontrollkästchen der **Verbunddokumente** Seite des Assistenten für die MFC-Anwendung. Weitere Informationen finden Sie unter [Erstellen einer Containeranwendung für aktive Dokumente](../mfc/creating-an-active-document-container-application.md).

Weitere Informationen zu active Document-Container finden Sie unter:

- [Containeranforderungen](#container_requirements)

- [Website-Dokumentobjekte](#document_site_objects)

- [Website-Objekte anzeigen](#view_site_objects)

- [Rahmenobjekt](#frame_object)

- [Verschachteln des Hilfemenüs](../mfc/help-menu-merging.md)

- [Programmgesteuertes Drucken](../mfc/programmatic-printing.md)

- [Befehlsziele](../mfc/message-handling-and-command-targets.md)

##  <a name="container_requirements"></a> Containeranforderungen

Active Document-Unterstützung in active Document-Container bedeutet mehr als nur schnittstellenimplementierungen: Es sind auch Kenntnisse über die Schnittstellen des enthaltenen Objekts. Das gleiche gilt für aktive dokumenterweiterungen, in denen der Container verwenden Sie die Schnittstellen der datenverarbeitungserweiterung auf die aktive Dokumente selbst auch wissen muss.

Müssen ein active Document-Container, der aktive Dokumente integriert ist:

- Objektspeicher über in der Lage sein den `IPersistStorage` -Schnittstelle, d. h., er muss Bereitstellen einer `IStorage` Instanz für jedes active Document.

- Die grundlegende Einbettungsfunktionen von OLE-Dokumenten "Website"-Objekte (einer pro-Dokument oder einbetten) zu unterstützen, implementieren `IOleClientSite` und `IAdviseSink`.

- Direkte Aktivierung von eingebetteten Objekten oder aktive Dokumente zu unterstützen. Standortobjekte des Containers müssen implementieren `IOleInPlaceSite` rahmenobjekt des Containers bereitstellen muss `IOleInPlaceFrame`.

- Unterstützen Sie die aktive Dokumente-Erweiterungen durch Implementieren von `IOleDocumentSite` auf den Mechanismus für den Container für die Kommunikation auf das Dokument bereitstellt. Optional kann die Container active Document-Schnittstellen implementieren `IOleCommandTarget` und `IContinueCallback` übernimmt diese einfache Befehle wie z. B. drucken oder speichern.

Die Frame-Objekt, die Objekte anzeigen und Container-Objekt können optional implementieren `IOleCommandTarget` zur Unterstützung der Verteilungs bestimmte Befehle, wie unter [Befehlsziele](../mfc/message-handling-and-command-targets.md). Anzeigen und Container-Objekte können optional auch implementieren `IPrint` und `IContinueCallback`, um die programmgesteuerte drucken zu unterstützen, wie unter [den programmatischen Druck](../mfc/programmatic-printing.md).

Die folgende Abbildung zeigt die konzeptionelle Beziehung zwischen einem Container und seine Komponenten (auf der linken Seite), und das aktive Dokument und seinen Ansichten (rechts). Das aktive Dokument verwaltet, Speicher und Daten, und die Ansicht zeigt oder gibt optional die Daten. Schnittstellen in Fettdruck sind diejenigen, die für die Teilnahme des aktiven Dokuments erforderlich; Die fett und kursiv sind optional. Alle anderen Schnittstellen sind erforderlich.

![Active Document-Containerschnittstellen](../mfc/media/vc37gj1.gif "Active Document-Container-Schnittstellen")

Ein Dokument, das nur eine einzige Ansicht unterstützt, kann die Ansicht und die Dokument-Komponenten (d. h. die entsprechenden Schnittstellen) auf einer einzigen konkreten Klasse implementieren. Darüber hinaus kann eine Containerwebsite, die nur eine Ansicht zu einem Zeitpunkt unterstützt das Dokument und dem Standort anzeigen in einer einzigen konkreten-Standort-Klasse kombinieren. Rahmenobjekt des Containers, muss jedoch unterschiedliche bleiben, und die Komponente für den Container lediglich befindet sich hier um ein vollständiges Bild von der Architektur zu ermöglichen; Es ist nicht betroffen von der active Document Containment-Architektur.

##  <a name="document_site_objects"></a> Website-Dokumentobjekte

In der active Document Containment-Architektur, eine Website ist identisch mit einer Client-Standortobjekt im OLE-Dokumente durch das Hinzufügen von der `IOleDocument` Schnittstelle:

```cpp
interface IOleDocumentSite : IUnknown
{
    HRESULT ActivateMe(IOleDocumentView *pViewToActivate);
}
```

Die Website ist vom Konzept her der Container für eine oder mehrere "Website anzeigen"-Objekte. Jedes Sichtobjekt für den Standort bezieht sich auf einzelne Ansichtsobjekte, der das Dokument von der Website verwaltet werden. Wenn der Container nur eine Ansicht pro dokumentensite unterstützt, können sie die Website und die View-Website mit einer einzigen konkreten Klasse implementieren.

##  <a name="view_site_objects"></a> Website-Objekte anzeigen

Ansicht-Site-Objekt eines Containers verwaltet den Anzeigebereich für eine bestimmte Ansicht eines Dokuments. Zusätzlich zur Unterstützung des Standards `IOleInPlaceSite` -Schnittstelle, ein Standort für die Ansicht auch in der Regel implementiert `IContinueCallback` für den programmatischen Druck-Steuerelement. (Beachten Sie, die das Objekt nie für Abfragen `IContinueCallback` , damit sie tatsächlich implementiert werden kann, auf alle Objekte der Container Wünsche.)

Ein Container, der mehrere Ansichten unterstützt, muss mehrere Ansichten Standortobjekte innerhalb der Website erstellen können. Dadurch kann jede Ansicht mit separaten-Aktivierung und-Deaktivierung-Diensten, wie angegeben über `IOleInPlaceSite`.

##  <a name="frame_object"></a> Rahmenobjekt

Rahmenobjekt des Containers ist zum größten Teil desselben Frames, die für die direkte Aktivierung in OLE-Dokumenten, d. h. verwendet wird, die Menü- und Symbolleistenobjekte Aushandlung behandelt. Ein-Objekt hat Zugriff auf diese rahmenobjekt über `IOleInPlaceSite::GetWindowContext`, die bietet außerdem Zugriff auf das Containerobjekt, das Containerdokument (der Bereich auf Serverebene Symbolleiste-Aushandlung und die darin enthaltenen Objektenumeration verarbeiten kann) darstellt.

Active Document-Container kann Frames erweitern, indem Sie die hinzufügen `IOleCommandTarget`. Dadurch kann er für Befehle zu empfangen, die in der Benutzeroberfläche im aktiven Dokument auf die gleiche Weise stammen, dass diese Schnittstelle einen Container für die gleichen Befehle senden kann (z. B. **Datei neu**, **öffnen**,  **Speichern Sie als**, **Drucken**; **Kopie bearbeiten**, **einfügen**, **Rückgängig**, usw.), eines aktiven Dokuments. Weitere Informationen finden Sie unter [Befehlsziele](../mfc/message-handling-and-command-targets.md).

## <a name="see-also"></a>Siehe auch

[Aktive Dokumente-Container](../mfc/active-document-containment.md)
