---
title: Frame-Fensterklassen (Architektur) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.frame
dev_langs:
- C++
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7de72b77be9be90ca876cfef943500a0312d183
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="frame-window-classes-architecture"></a>Klassen für Rahmenfenster (Architektur)
In Dokument-/Ansichtarchitektur sind Rahmenfenster Fenster, die Fenster "ein" enthalten. Außerdem unterstützen Sie steuern müssen Balken angefügt werden.  
  
 In mehreren Document Interface (MDI)-Anwendungen wird im Hauptfenster von abgeleitet `CMDIFrameWnd`. Darin ist die Dokumente Frames, die indirekt `CMDIChildWnd` Objekte. Die `CMDIChildWnd` Objekte wiederum enthalten, die Dokumente Ansichten.  
  
 In Anwendungen für einzelnes Dokument Interface (SDI), klicken Sie im Hauptfenster abgeleitet `CFrameWnd`, enthält die Sicht des aktuellen Dokuments.  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 Die Basisklasse für eine SDI-Anwendung Hauptrahmenfenster. Auch die Basisklasse für alle anderen Klassen für Rahmenfenster.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 Die Basisklasse für eine MDI-Anwendung Hauptrahmenfenster.  
  
 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
 Die Basisklasse für eine MDI-Anwendung Dokumentrahmenfenster.  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 Stellt das Rahmenfenster für eine Sicht, wenn Serverdokument direkt bearbeitet wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

