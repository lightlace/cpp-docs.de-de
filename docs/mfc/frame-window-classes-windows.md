---
title: Frame-Klassen (Windows) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.frame
dev_langs:
- C++
helpviewer_keywords:
- frame window classes [MFC], reference
ms.assetid: 6342ec5f-f922-4da8-a78e-2f5f994c7142
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c2668a8334192d4de199f1c42a648b74add1ca5c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="frame-window-classes-windows"></a>Klassen für Rahmenfenster (Windows)
Frame-Fenster sind Fenster, die eine Anwendung oder einen Teil einer Anwendung frame. Rahmenfenster enthalten normalerweise die anderen Fenster, z. B. Sichten, Symbolleisten und Statusleisten. Im Fall von `CMDIFrameWnd`, sie enthalten möglicherweise `CMDIChildWnd` indirekt Objekte.  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 Die Basisklasse für eine SDI-Anwendung Hauptrahmenfenster. Auch die Basisklasse für alle anderen Klassen für Rahmenfenster.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 Die Basisklasse für eine MDI-Anwendung Hauptrahmenfenster.  
  
 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
 Die Basisklasse für eine MDI-Anwendung Dokumentrahmenfenster.  
  
 [CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md)  
 Ein halber Höhe Frame-Fenster, das in der Regel um unverankerte Symbolleisten sichtbar ist.  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 Stellt das Rahmenfenster für eine Sicht, wenn Serverdokument direkt bearbeitet wird.  
  
## <a name="related-class"></a>Verknüpfte Klasse aus  
 Klasse `CMenu` stellt eine Schnittstelle, über die Menüs für die Anwendung zugreifen. Dies ist nützlich für das Bearbeiten von Menüs dynamisch zur Laufzeit; z. B. beim Hinzufügen oder Löschen von Menüelementen je nach Kontext. Obwohl Menüs mit Frame-Fensters am häufigsten verwendet werden, können sie auch mit den Dialogfeldern und anderen nicht untergeordneten Fenstern verwendet werden.  
  
 [CMenu](../mfc/reference/cmenu-class.md)  
 Kapselt eine `HMENU` Handle für der Anwendungsverzeichnis Menü- und Popupmenüs.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

