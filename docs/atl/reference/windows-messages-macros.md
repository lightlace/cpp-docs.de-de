---
title: Windows-Nachrichten Makros | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::WM_FORWARDMSG
dev_langs:
- C++
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 21bb273b94f871e253ab927238c96256f46e2b3a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="windows-messages-macros"></a>Windows-Nachrichten Makros
Dieses Makro werden fenstermeldungen weitergeleitet.  
  
|||  
|-|-|  
|[WM_FORWARDMSG](#wm_forwardmsg)|Verwenden Sie zum Weiterleiten einer Nachricht von einem Fenster in ein anderes Fenster für die Verarbeitung empfangen.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h 
   
##  <a name="wm_forwardmsg"></a>  WM_FORWARDMSG  
 Dieses Makro leitet eine Nachricht empfangen, die von einem Fenster in ein anderes Fenster für die Verarbeitung.  
  
```
WM_FORWARDMSG
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Meldung verarbeitet wurde, NULL, wenn nicht.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `WM_FORWARDMSG` weiterleiten eine Nachricht von einem Fenster in ein anderes Fenster für die Verarbeitung empfangen. Die LPARAM und WPARAM-Parameter werden wie folgt verwendet:  
  
|Parameter|Verwendung|  
|---------------|-----------|  
|WPARAM|Vom Benutzer definierten Datentyps|  
|LPARAM|Ein Zeiger auf eine `MSG` -Struktur, die Informationen zu einer Meldung enthält.|  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel `m_hWndOther` stellt dar, das andere Fenster, die diese Nachricht empfangen hat.  
  
 [!code-cpp[NVC_ATL_Windowing#137](../../atl/codesnippet/cpp/windows-messages-macros_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)
