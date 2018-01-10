---
title: Von Animationssteuerelementen gesendete Benachrichtigungen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c57a33bf4b13397d4f296ef4e5aa8e137c2d3594
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="notifications-sent-by-animation-controls"></a>Von Animationssteuerelementen gesendete Benachrichtigungen
Eines Animationssteuerelements ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)) zwei verschiedene Arten von Benachrichtigungen sendet. Die Benachrichtigungen werden gesendet, in Form von [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachrichten.  
  
 Die [ACN_START](http://msdn.microsoft.com/library/windows/desktop/bb761891) Nachricht wird gesendet, wenn die Animation-Steuerelement einen Clip-Wiedergabe gestartet wurde. Die [ACN_STOP](http://msdn.microsoft.com/library/windows/desktop/bb761893) Nachricht wird gesendet, wenn die Animationssteuerelements abgeschlossen oder einen Clip-Wiedergabe beendet wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CAnimateCtrl](../mfc/using-canimatectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

