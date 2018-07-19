---
title: Globale Funktionen für die Ereignisbehandlung | Microsoft-Dokumentation
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
ms.openlocfilehash: 85babf3155fdc94dafd5d62c2e67401e5add3663
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883998"
---
# <a name="event-handling-global-functions"></a>Globale Funktionen für Ereignis behandeln
Diese Funktion bietet es sich um einen Ereignishandler.  
  
> [!IMPORTANT]
>  Die Funktion, die in der folgenden Tabelle aufgeführten kann nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
|||  
|-|-|  
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|Wartet auf ein Objekt, das signalisiert werden, Unterdessen fenstermeldungen nach Bedarf.|  

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
 *hEvent*  
 [in] Das Handle des Objekts, die gewartet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, wenn das Objekt signalisiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist nützlich, wenn Sie warten, bis ein Ereignis eines Objekts auftreten, und es geschieht benachrichtigt werden möchten, aber Windows-Meldungen während des Wartens verteilt werden können.  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)
