---
title: Struktur von Benachrichtigungsmeldungen des Registersteuerelements | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- notifications [MFC], tree controls
- messages [MFC], notification
- CTreeCtrl class [MFC], notifications
- notifications [MFC], CTreeCtrl
- tree controls [MFC], notification messages
ms.assetid: ac7013b4-91dd-4668-bd75-439ca0680ef9
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e5044416ca38f6b3ead743c571ea7175022d51fe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tree-control-notification-messages"></a>Benachrichtigungsmeldungen von Struktursteuerelementen
Ein Strukturansicht-Steuerelement ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) sendet die folgenden benachrichtigungsmeldungen als **WM_NOTIFY** Nachrichten:  
  
|Benachrichtigungsmeldung|Beschreibung|  
|--------------------------|-----------------|  
|**TVN_BEGINDRAG**|Signalisiert den Start eines Drag-and-Drop-Vorgangs|  
|**TVN_BEGINLABELEDIT**|Signalisiert den Beginn der direkten Bezeichnung bearbeiten|  
|**TVN_BEGINRDRAG**|Signalisiert den Start eines Drag-and-Drop-Vorgangs, mit der rechten Maustaste|  
|**TVN_DELETEITEM**|Signalisiert das Löschen eines bestimmten Elements|  
|**TVN_ENDLABELEDIT**|Signalisiert das Ende der Bezeichnung bearbeiten|  
|**TVN_GETDISPINFO**|Fordert Informationen, dass das Strukturansicht-Steuerelement erfordert ein Element angezeigt wird|  
|**TVN_ITEMEXPANDED**|Signalisiert, dass ein übergeordnetes Element der Liste der untergeordneten Elemente erweitert oder reduziert wurde|  
|**TVN_ITEMEXPANDING**|Signalisiert, dass ein übergeordnetes Element der Liste der untergeordneten Elemente erweitert oder reduziert|  
|**TVN_KEYDOWN**|Signalisiert ein Tastaturereignis|  
|**EINE TVN_SELCHANGED**|Signale, die die Auswahl von einem Element in eine andere geändert wurden|  
|**TVN_SELCHANGING**|Signalisiert, dass die Auswahl von einem Element in eine andere geändert werden|  
|**TVN_SETDISPINFO**|Benachrichtigung zum Aktualisieren der Informationen für ein Element verwaltet|  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

