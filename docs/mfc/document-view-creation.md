---
title: Dokument-/-Erstellung
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], creating
- views [MFC], and frame windows
- views [MFC], creating
- tables [MFC]
- MFC, views
- document/view architecture [MFC], creating document/view
- object creators
- MFC, documents
- tables [MFC], objects each MFC object creates
ms.assetid: bda14f41-ed50-439d-af9e-591174e7dd64
ms.openlocfilehash: eccc65df784d000f8dccc244e295da522658b626
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633558"
---
# <a name="documentview-creation"></a>Erstellen von Dokument/Ansicht

Das Framework stellt Implementierungen von der **neu** und **öffnen** Befehle (unter anderem) die **Datei** Menü. Erstellen eines neuen Dokuments zugeordnete Ansicht und der zugehörigen Rahmenfenster ist eine gemeinschaftliche Arbeit zwischen dem Application-Objekt, eine Dokumentvorlage, das gerade erstellte Dokument und das neu erstellte Rahmenfenster. Die folgende Tabelle fasst zusammen, welche Objekte was erstellen.

### <a name="object-creators"></a>Objektersteller

|Creator|Wird erstellt|
|-------------|-------------|
|Application-Objekt|Dokumentvorlage|
|Dokumentvorlage|Dokument|
|Dokumentvorlage|Rahmenfenster|
|Rahmenfenster|Ansicht|

## <a name="see-also"></a>Siehe auch

[Dokumentvorlagen und der Erstellungsvorgang für Dokumente und Ansichten](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[Erstellen von Dokumentvorlagen](../mfc/document-template-creation.md)<br/>
[Beziehungen zwischen MFC-Objekten](../mfc/relationships-among-mfc-objects.md)<br/>
[Erstellen neuer Dokumente, Fenster und Ansichten](../mfc/creating-new-documents-windows-and-views.md)

