---
title: Von Animationssteuerelementen gesendete Benachrichtigungen | Microsoft-Dokumentation
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
ms.openlocfilehash: d7aff43577a4b1aa55fc0725ba4753228e334000
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43199660"
---
# <a name="notifications-sent-by-animation-controls"></a>Von Animationssteuerelementen gesendete Benachrichtigungen
Ein Animationssteuerelement ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)) zwei verschiedene Arten von Benachrichtigungen sendet. Die Benachrichtigungen werden gesendet, in Form von [WM_COMMAND](/windows/desktop/menurc/wm-command) Nachrichten.  
  
 Die [ACN_START](/windows/desktop/Controls/acn-start) Nachricht wird gesendet, wenn das Animationssteuerelement gestartet wurde, einen Audioclip abspielen. Die [ACN_STOP](/windows/desktop/Controls/acn-stop) Nachricht wird gesendet, wenn das Animationssteuerelement abgeschlossen oder beendet einen Audioclip abspielen.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CAnimateCtrl](../mfc/using-canimatectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

