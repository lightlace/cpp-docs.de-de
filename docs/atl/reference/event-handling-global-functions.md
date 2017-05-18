---
title: "Globale Funktionen für die Ereignisbehandlung | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 4bf2a8b0211361f5d5d2bf0f996e978638631116
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="event-handling-global-functions"></a>Globale Funktionen zur Verarbeitung von Ereignis
Diese Funktion bietet einen Ereignishandler.  
  
> [!IMPORTANT]
>  Die Funktion, die in der folgenden Tabelle aufgeführten kann nicht verwendet werden, in der Anwendung, die in ausgeführt der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|Wartet auf ein Objekt, das signalisiert werden Unterdessen fenstermeldungen nach Bedarf.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  

##  <a name="atlwaitwithmessageloop"></a>AtlWaitWithMessageLoop  
 Wartet auf die Signalisierung des Objekts und leitet unterdessen Fenstermeldungen nach Bedarf weiter.  
  
> [!IMPORTANT]
>  Diese Funktion kann nicht verwendet werden, in Anwendungen, die in Ausführen der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```  
  
### <a name="parameters"></a>Parameter  
 `hEvent`  
 [in] Das Handle des Objekts zu warten.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** , wenn das Objekt signalisiert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist hilfreich, wenn Sie warten, bis ein Objekt Ereignis stattgefunden hat, und es benachrichtigt werden möchten, aber Fenster Nachrichten während des Wartens weitergeleitet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)

