---
title: "MFC-Anwendungsarchitekturklassen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.mfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anwendungsarchitekturklassen"
  - "Klassen [C++], MFC"
  - "MFC [C++], Anwendungsentwicklung"
  - "MFC [C++], Klassen"
ms.assetid: 71b2de54-b44d-407e-9c71-9baf954e18d9
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# MFC-Anwendungsarchitekturklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Klassen in dieser Kategorie tragen zur Architektur einer Framework\-Anwendung bei.  Sie bieten Funktionen für die meisten Anwendungen.  Sie füllen das Framework aus, um anwendungsspezifische Funktionen hinzuzufügen.  In der Regel erfolgt dies, indem Sie neue Klassen von Architekturklassen berechnen, und anschließend neue Member hinzufügen oder vorhandene Memberfunktionen überschreiben.  
  
 [Anwendungs\-Assistenten](../mfc/reference/mfc-application-wizard.md) generieren verschiedene Arten von Anwendungen, die das Anwendungsframework auf Unterscheidungsarten verwenden.  Anwendungen SDI \(Single Document Interface\) und MDI \(Multiple Document Interface\) können alle mit einem Bestandteil des Frameworks, das Unterstützung aufgerufen wird.  Andere Anwendungstypen, wie auf Dialogfeldern basierende Anwendungen, formularbasierte Anwendungen und DLLs, verwenden nur einige der Dokument\-\/Ansichtsarchitektur\-Funktionen.  
  
 Dokument\/Ansichts\-Anwendungen enthalten eine oder mehrere Sätze Dokumente, Ansichten und Rahmenfenster.  Ein Dokumentvorlagenobjekt ordnet die Klassen für jeden Dokument\/Ansichts\-\/Framesatz zu.  
  
 Obwohl Sie in der MFC\-Anwendung Dokument\-\/Ansichtarchitektur nicht verwenden müssen, gibt es mehrere Vorteile zu tun.  Die Container\- und Serverunterstützung MFC\-OLE basiert auf der Dokument\-\/Ansichtarchitektur, beispielsweise zum Drucken und Druckvorschau ist.  
  
 Alle MFC\-Anwendungen haben mindestens zwei Objekte: ein Anwendungsobjekt wird von [CWinApp](../mfc/reference/cwinapp-class.md) abgeleitet und jede Art Hauptfensterobjekts, berechnet \(häufig indirekt von [CWnd](../mfc/reference/cwnd-class.md). \(Am häufigsten, wird das Hauptfenster von [CFrameWnd](../mfc/reference/cframewnd-class.md), [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) oder von [CDialog\-Klasse](../mfc/reference/cdialog-class.md) abgeleitet wird, die von `CWnd` abgeleitet werden\).  
  
 Anwendungen, die Dokument\-\/Ansichtarchitektur verwenden, enthalten zusätzliche Objekte.  Die hauptsächlich sind:  
  
-   Ein Anwendungsobjekt wird von der [CWinApp](../mfc/reference/cwinapp-class.md)\- Klasse, wie zuvor erwähnt.  
  
-   Eine oder mehrere Dokumentklassenobjekte abgeleitet von der [CDocument](../mfc/reference/cdocument-class.md).  Dokumentklassenobjekte sind für die interne Repräsentation der Daten verwendet, die in der Ansicht bearbeitet werden.  Sie werden mit einer Datendatei zugeordnet werden.  
  
-   Mindestens Ansichtsobjekte abgeleitet von der [CView](../mfc/reference/cview-class.md).  Jede Ansicht ist ein Fenster, das einem Dokument angefügt ist und mit einem Rahmenfenster zugeordnet.  Ansichten zeigen und Bearbeiten der Daten, die in einem Dokumentklassenobjekt enthalten sind.  
  
 Dokument\/Ansichts\-Anwendungen enthalten auch die Rahmenfenster \(abgeleitet von [CFrameWnd](../mfc/reference/cframewnd-class.md)\) und die Dokumentvorlagen \(abgeleitet von [CDocTemplate](../mfc/reference/cdoctemplate-class.md)\).  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)