---
title: Dokument-Ansicht erstellen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c6997189f23ea7599dde0a1b19ba9f0ea350378d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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

