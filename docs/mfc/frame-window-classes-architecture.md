---
title: Frame-Fensterklassen (Architektur) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.frame
dev_langs: C++
helpviewer_keywords: frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0b4a8076cbec9292718c9bc2413d690bacbc4a67
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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

