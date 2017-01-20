---
title: "Benachrichtigungsmeldungen von Struktursteuerelementen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTreeCtrl-Klasse, Benachrichtigungen"
  - "Meldungen, Benachrichtigung"
  - "Benachrichtigungen, CTreeCtrl"
  - "Benachrichtigungen, Struktursteuerelemente"
  - "Struktursteuerelemente, Benachrichtigungsmeldungen"
ms.assetid: ac7013b4-91dd-4668-bd75-439ca0680ef9
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Benachrichtigungsmeldungen von Struktursteuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Strukturansicht \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) sendet die folgenden Benachrichtigungsmeldungen als **WM\_NOTIFY** Meldungen:  
  
|Benachrichtigung|**Beschreibung**|  
|----------------------|----------------------|  
|**TVN\_BEGINDRAG**|Signalisiert dem Start eines Drag & Drop\-Vorgangs|  
|**TVN\_BEGINLABELEDIT**|Signalisiert dem Anfang der direkten Bezeichnungsbearbeitung|  
|**TVN\_BEGINRDRAG**|Signalisiert dem Start eines Drag & Drop\-Vorgangs, mit der rechten Maustaste|  
|**TVN\_DELETEITEM**|Signalisiert dem Löschen eines bestimmten Elements|  
|**TVN\_ENDLABELEDIT**|Signalisiert dem Ende der Bezeichnungsbearbeitung|  
|**TVN\_GETDISPINFO**|Fordert Informationen an, die das Struktursteuerelement erforderlich, um ein Element anzuzeigen|  
|**TVN\_ITEMEXPANDED**|Signalisiert, dass die Liste eines übergeordneten Elements der untergeordneten Elemente erweitert oder reduziert wurde|  
|**TVN\_ITEMEXPANDING**|Signalisiert, dass die Liste eines übergeordneten Elements von untergeordneten Elementen im Begriff ist erweitert werden oder reduziert werden|  
|**TVN\_KEYDOWN**|Signalisiert ein Tastaturereignis|  
|**TVN\_SELCHANGED**|Signalisiert, dass die Auswahl von einem Element zum anderen geändert hat|  
|**TVN\_SELCHANGING**|Signalisiert, dass die Markierung im Begriff ist, von einem Element zum anderen geändert werden|  
|**TVN\_SETDISPINFO**|Benachrichtigung, um die Informationen aktualisieren verwaltet für ein Element|  
  
## Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)