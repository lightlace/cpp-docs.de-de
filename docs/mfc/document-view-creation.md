---
title: Dokument-Ansicht erstellen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb89180db8e1a6cce2c40bbb4bae0965b972afa2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="documentview-creation"></a>Erstellen von Dokument/Ansicht
Das Framework stellt Implementierungen von der `New` und **öffnen** Befehle (u. a.) den **Datei** Menü. Erstellen eines neuen Dokuments zugeordnete Ansicht und der zugehörigen Rahmenfenster ist ein kooperativen Aufwand für das Anwendungsobjekt, eine Dokumentvorlage, das gerade erstellte Dokument und das neu erstellte Rahmenfenster. Die folgende Tabelle fasst zusammen, welche Objekte erstellen, was.  
  
### <a name="object-creators"></a>Objektersteller  
  
|Creator|Erstellt|  
|-------------|-------------|  
|Application-Objekt|Dokumentvorlage|  
|Dokumentvorlage|Dokument|  
|Dokumentvorlage|Rahmenfenster|  
|Rahmenfenster|Ansicht|  
  
## <a name="see-also"></a>Siehe auch  
 [Dokumentvorlagen und der Erstellungsvorgang für die Dokument-/Ansichtarchitektur](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Erstellen von Dokumentvorlagen](../mfc/document-template-creation.md)   
 [Beziehungen zwischen MFC-Objekte](../mfc/relationships-among-mfc-objects.md)   
 [Erstellen neuer Dokumente, Fenster und Ansichten](../mfc/creating-new-documents-windows-and-views.md)

