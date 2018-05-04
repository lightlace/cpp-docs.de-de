---
title: Globale Funktionen für die Ereignisbehandlung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlWaitWithMessageLoop
dev_langs:
- C++
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb2c7834e7d5475810973a42ef179ea4f5f0079f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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

##  <a name="atlwaitwithmessageloop"></a>  AtlWaitWithMessageLoop  
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
