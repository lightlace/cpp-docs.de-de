---
title: "Globale Funktionen für die Ereignisbehandlung | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: atlbase/ATL::AtlWaitWithMessageLoop
dev_langs: C++
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 747704bb271c294728832c8ee8108da458c739ba
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="event-handling-global-functions"></a>Ereignis globale Funktionen
Diese Funktion bietet einen Ereignishandler.  
  
> [!IMPORTANT]
>  Die Funktion, die in der folgenden Tabelle aufgeführten kann nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
|||  
|-|-|  
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|Wartet auf ein Objekt auf die Signalisierung, Unterdessen fenstermeldungen nach Bedarf.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  

##  <a name="atlwaitwithmessageloop"></a>AtlWaitWithMessageLoop  
 Wartet auf die Signalisierung des Objekts und leitet unterdessen Fenstermeldungen nach Bedarf weiter.  
  
> [!IMPORTANT]
>  Diese Funktion kann nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```  
  
### <a name="parameters"></a>Parameter  
 `hEvent`  
 [in] Das Handle des Objekts gewartet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** , wenn das Objekt signalisiert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist hilfreich, wenn Sie ein Objekt Ereignisses ausgeführt werden und davon geschieht benachrichtigt werden möchten, aber ermöglichen fenstermeldungen beim Warten, gesendet werden soll.  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)
