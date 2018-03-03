---
title: MFC-Anwendungsarchitekturklassen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.mfc
dev_langs:
- C++
helpviewer_keywords:
- MFC, classes
- MFC, application development
- classes [MFC], MFC
- application architecture classes [MFC]
ms.assetid: 71b2de54-b44d-407e-9c71-9baf954e18d9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 623775d6c3306ba4afdb01eb78ea70b05f7a3365
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-application-architecture-classes"></a>Klassen der MFC-Anwendungsarchitektur
Klassen in dieser Kategorie beitragen, die Architektur der Framework-Anwendung. Sie geben die Funktionen, die meisten Anwendungen. Füllen Sie das Framework anwendungsspezifische Funktionen hinzufügen. In der Regel führen Sie dies durch den Architektur-Klassen neue Klassen ableiten und dann neue Elemente hinzufügen oder vorhandene Memberfunktionen überschreiben.  
  
 [Anwendungsassistenten](../mfc/reference/mfc-application-wizard.md) generieren Sie mehrere Typen von Anwendungen, von denen alle Anwendungsframeworks auf unterschiedliche Weise verwenden. Stellen SDI (Einzeldokumentoberfläche) und MDI (MDI)-Anwendungen optimal nutzen eines Teils des Frameworks Dokument-/Ansichtarchitektur aufgerufen. Andere Typen von Anwendungen, z. B. auf Dialogfeldern basierende Anwendungen, formularbasierte Anwendungen und DLLs, verwenden Sie nur einige der Funktionen der Dokument-/Ansichtarchitektur-Architektur.  
  
 Dokument-/ansichtsanwendungen enthalten eine oder mehrere Sätze von Dokumente, Ansichten und Rahmenfenster. Eine Dokumentvorlagenobjekt ordnet die Klassen für jeden Satz von Dokument/Ansicht/Frame.  
  
 Obwohl Sie keine Dokument-/Ansichtarchitektur in der MFC-Anwendung verwenden, stehen eine Reihe von Vorteilen zu tun. Die MFC-OLE-Container und Server Unterstützung basiert auf Dokument-/Ansichtarchitektur wie ist die Unterstützung für Drucken und Druckvorschau.  
  
 Alle MFC-Anwendungen verfügen über mindestens zwei Objekte: ein Anwendungsobjekt abgeleitet [CWinApp](../mfc/reference/cwinapp-class.md), und im Hauptfenster-Objekt (häufig indirekt) abgeleitet irgendeine [CWnd](../mfc/reference/cwnd-class.md). (In den meisten Fällen wird im Hauptfenster von abgeleitet [CFrameWnd](../mfc/reference/cframewnd-class.md), [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), oder [CDialog](../mfc/reference/cdialog-class.md), wobei alle abgeleitet sind `CWnd`.)  
  
 Anwendungen, die Dokument-/Ansichtarchitektur verwenden werden zusätzliche Objekte enthalten. Principal-Objekte sind:  
  
-   Ein Anwendungsobjekt abgeleitet Klasse [CWinApp](../mfc/reference/cwinapp-class.md), wie bereits zuvor erwähnt.  
  
-   Eine oder mehrere-Klasse Dokumentobjekte von Klasse abgeleitet [CDocument](../mfc/reference/cdocument-class.md). -Klasse Dokumentobjekte sind verantwortlich für die interne Darstellung der Daten in der Ansicht bearbeitet. Sie können eine Datendatei zugeordnet werden.  
  
-   Eine oder mehrere Objekte, die von Klasse abgeleitet [CView](../mfc/reference/cview-class.md). Jede Ansicht ist ein Fenster, das an ein Dokument angefügt und einem Rahmenfenster zugeordnet ist. Ansichten anzeigen und bearbeiten die Daten in ein Dokument-Klassenobjekt.  
  
 Dokument-/ansichtsanwendungen enthalten auch Rahmenfenster (abgeleitet [CFrameWnd](../mfc/reference/cframewnd-class.md)) und Dokumentvorlagen (abgeleitet [CDocTemplate](../mfc/reference/cdoctemplate-class.md)).  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

