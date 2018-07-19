---
title: Verarbeiten von Benachrichtigungen des Headersteuerelements | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CHeaderCtrl class [MFC], processing notifications
- controls [MFC], header
- notifications [MFC], processing for CHeaderCtrl
- header controls [MFC], processing notifications
- header control notifications
ms.assetid: e6c6af7c-d458-4d33-85aa-48014ccde5f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a0fe657089c33679cf8d18f95268a70335804c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348890"
---
# <a name="processing-header-control-notifications"></a>Verarbeiten von Benachrichtigungen des Headersteuerelements
Verwenden Sie in Ihrer Klasse Ansichts- oder Dialogfeldobjekt des Eigenschaftenfensters zum Erstellen einer [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) Handlerfunktion mit einer Switch-Anweisung für eine beliebige Headersteuerelement ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) benachrichtigungsmeldungen werden sollen verarbeiten (siehe [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)). Benachrichtigungen werden an das übergeordnete Fenster gesendet, wenn der Benutzer klickt oder ein Headerelement zieht ein Unterteiler zwischen Elementen und So weiter doppelklickt.  
  
 In die benachrichtigungsmeldungen verknüpft sind, mit dem Headersteuerelement aufgelisteten [Header Kontrollverweis](http://msdn.microsoft.com/library/windows/desktop/bb775239) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

