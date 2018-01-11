---
title: Rahmenfensterklassen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- frame window classes [MFC], about frame window classes
- frame window classes [MFC]
- windows [MFC], MDI
- document frame windows [MFC], classes
- single document interface (SDI), frame windows
- window classes [MFC], frame
- MFC, frame windows
- MDI [MFC], frame windows
- classes [MFC], window
ms.assetid: c27e43a7-8ad0-4759-b1b7-43f4725f4132
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b5e67ef155c029285d0b306ca2d05179e993de78
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="frame-window-classes"></a>Rahmenfensterklassen
Jede Anwendung hat eine "Hauptrahmenfenster," einem Desktopfenster aus, die in der Regel den Namen der Anwendung in die Beschriftung besitzt. Jedes Dokument ist normalerweise auf eine "Dokumentrahmenfenster." Einem Dokumentrahmenfenster enthält mindestens eine Sicht, die Daten des Dokuments dargestellt.  
  
## <a name="frame-windows-in-sdi-and-mdi-applications"></a>Rahmenfenster im SDI und MDI-Anwendungen  
 Für eine SDI-Anwendung besteht eine Rahmenfenster Klasse abgeleitet [CFrameWnd](../mfc/reference/cframewnd-class.md). Dieses Fenster ist sowohl das Hauptrahmenfenster und die Dokumentrahmenfenster. Für eine Anwendung MDI-Hauptrahmenfenster Klasse abgeleitet [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), und die Frame-Dokumentfenster, das untergeordneten MDI-Fenster sind, von der Klasse abgeleitet sind [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md).  
  
## <a name="use-the-frame-window-class-or-derive-from-it"></a>Verwenden Sie die Frame-Fensterklasse oder daraus abgeleitet werden  
 Diese Klassen bieten die meisten Rahmenfenster Funktionen, die Sie für Ihre Anwendungen benötigen. Unter normalen Umständen werden das Standardverhalten und die Darstellung, die sie bereitstellen, die Ihren Anforderungen entsprechend. Wenn Sie zusätzliche Funktionen benötigen, leiten Sie von diesen Klassen.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Vom Anwendungs-Assistenten erstellte Rahmenfensterklassen](../mfc/frame-window-classes-created-by-the-application-wizard.md)  
  
-   [Rahmenfensterstile](../mfc/frame-window-styles-cpp.md)  
  
-   [Ändern der Stile eines mit MFC erstellten Fensters](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Rahmenfenster](../mfc/frame-windows.md)

