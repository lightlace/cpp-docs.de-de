---
title: Struktur von Benachrichtigungsmeldungen des Registersteuerelements | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], tree controls
- messages [MFC], notification
- CTreeCtrl class [MFC], notifications
- notifications [MFC], CTreeCtrl
- tree controls [MFC], notification messages
ms.assetid: ac7013b4-91dd-4668-bd75-439ca0680ef9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f7c352da9f9283f53c926a8223984620ee7fa6ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385735"
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

