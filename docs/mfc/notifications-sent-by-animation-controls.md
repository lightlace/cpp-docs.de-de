---
title: Von Animationssteuerelementen gesendete Benachrichtigungen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1696389ce3dc40c5d02ec660ebaeb6bf3e6c3ec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="notifications-sent-by-animation-controls"></a>Von Animationssteuerelementen gesendete Benachrichtigungen
Eines Animationssteuerelements ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)) zwei verschiedene Arten von Benachrichtigungen sendet. Die Benachrichtigungen werden gesendet, in Form von [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachrichten.  
  
 Die [ACN_START](http://msdn.microsoft.com/library/windows/desktop/bb761891) Nachricht wird gesendet, wenn die Animation-Steuerelement einen Clip-Wiedergabe gestartet wurde. Die [ACN_STOP](http://msdn.microsoft.com/library/windows/desktop/bb761893) Nachricht wird gesendet, wenn die Animationssteuerelements abgeschlossen oder einen Clip-Wiedergabe beendet wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CAnimateCtrl](../mfc/using-canimatectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

