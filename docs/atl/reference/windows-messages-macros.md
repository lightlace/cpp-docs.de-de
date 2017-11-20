---
title: Windows-Nachrichten Makros | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: atlbase/ATL::WM_FORWARDMSG
dev_langs: C++
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 66e212b1f8bd2e749bc87fec92b935aa466522b9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="windows-messages-macros"></a>Windows-Nachrichten Makros
Dieses Makro werden fenstermeldungen weitergeleitet.  
  
|||  
|-|-|  
|[WM_FORWARDMSG](#wm_forwardmsg)|Verwenden Sie zum Weiterleiten einer Nachricht von einem Fenster in ein anderes Fenster für die Verarbeitung empfangen.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h 
   
##  <a name="wm_forwardmsg"></a>WM_FORWARDMSG  
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
