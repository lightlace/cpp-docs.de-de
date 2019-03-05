---
title: Server für aktive Dokumente
ms.date: 11/04/2016
helpviewer_keywords:
- active documents [MFC], servers
- servers [MFC], active document
- active document servers [MFC]
ms.assetid: 131fec1e-02a0-4305-a7ab-903b911232a7
ms.openlocfilehash: 7050b810bb5e1f0c240222cd9b8c4922ced4238a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57270773"
---
# <a name="active-document-servers"></a>Server für aktive Dokumente

Server für aktive Dokumente wie z. B. Word, Excel oder PowerPoint-Host-Dokumente von anderen Anwendungstypen wird aufgerufen, aktive Dokumente. Im Gegensatz zu OLE eingebettete Objekte (die einfach auf der Seite von einem anderen Dokument angezeigt werden), aktive Dokumente enthalten, die komplette-Schnittstelle und die vollständige systemeigene Funktionalität der Serveranwendung, die sie erstellt. Benutzer können Dokumente erstellen, verwenden das volle Potenzial von ihre lieblingsanwendungen (Wenn sie aktive Dokument aktiviert sind), noch können behandeln das resultierende Projekt als einzelne Entität.

Aktive Dokumente können mehr als eine Seite und sind immer direkt aktiv. Aktive Dokumente steuern Teil der Benutzeroberfläche, indem Sie ihre Menüs mit der **Datei** und **Hilfe** Menüs des Containers. Sie nehmen den gesamten Bearbeitungsbereich des Containers und steuern die Ansichten und das Layout der Seite "Drucker" (Ränder, Fußzeilen und So weiter).

MFC implementiert Server für aktive Dokumente mit Dokument-/Ansicht-Schnittstellen, Befehl Dispatchzuordnungen, drucken, Menü-Management und registrierungsverwaltung. Anforderungen für bestimmte Programmiersprache finden Sie im [aktive Dokumente](../mfc/active-documents.md).

MFC unterstützt aktive Dokumente mit den [CDocObjectServer](../mfc/reference/cdocobjectserver-class.md) von abgeleitete Klasse [CCmdTarget](../mfc/reference/ccmdtarget-class.md), und [CDocObjectServerItem](../mfc/reference/cdocobjectserveritem-class.md), abgeleitet von [ COleServerItem](../mfc/reference/coleserveritem-class.md). MFC unterstützt active Document-Container mit dem [COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md) von abgeleitete Klasse [COleClientItem](../mfc/reference/coleclientitem-class.md).

`CDocObjectServer` wird, die das aktive Dokument und initialisiert und aktiviert ein active Document-Schnittstellen. MFC enthält außerdem Makros um Befehlsrouting in aktive Dokumente zu verarbeiten. Um aktive Dokumente in Ihrer Anwendung verwenden zu können, Sie AfxDocOb.h in der Datei "stdafx.h".

Ein reguläre MFC-Server verknüpft eine eigene `COleServerItem`-abgeleitete Klasse. Die MFS-Anwendungsassistenten generiert diese Klasse für die Sie bei Auswahl der **Mini-Servers** oder **Vollserver** Kontrollkästchen, um Ihre Anwendung Unterstützung für Verbunddokumente einzuräumen. Wenn Sie auch auswählen, die **Active Document-Server** Kontrollkästchen, die MFC-Anwendungs-Assistent erstellt eine Klasse abgeleitet `CDocObjectServerItem` stattdessen.

Die `COleDocObjectItem` Klasse ermöglicht, einen active Document-Container werden OLE-Container. Können Sie den Assistenten zum MFC-Anwendungen erstellen Sie einen active Document-Container durch Auswählen der **Active Document-Container** Kontrollkästchen in der Unterstützung für Verbunddokumente-Seite des Assistenten für MFC-Anwendung. Weitere Informationen finden Sie unter [Erstellen einer Containeranwendung für aktive Dokumente](../mfc/creating-an-active-document-container-application.md).

## <a name="see-also"></a>Siehe auch

[Aktive Dokumente-Container](../mfc/active-document-containment.md)
