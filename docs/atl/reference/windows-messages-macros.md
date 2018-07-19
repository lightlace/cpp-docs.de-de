---
title: Windows-Meldungen-Makros | Microsoft-Dokumentation
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
ms.openlocfilehash: 3063dd1bb5bbd9c0eb957b9727027b2d01edfd7d
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37886205"
---
# <a name="windows-messages-macros"></a>Windows-Meldungen-Makros
Dieses Makro leitet Windows-Meldungen.  
  
|||  
|-|-|  
|[WM_FORWARDMSG](#wm_forwardmsg)|Verwenden Sie eine Nachricht empfangen, die von einem Fenster in ein anderes Fenster zur Verarbeitung weitergeleitet.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h 
   
##  <a name="wm_forwardmsg"></a>  WM_FORWARDMSG  
 Dieses Makro leitet eine Nachricht von einem Fenster in ein anderes Fenster für die Verarbeitung empfangen.  
  
```
WM_FORWARDMSG
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Nachricht verarbeitet wurde, NULL, wenn nicht.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie WM_FORWARDMSG, um eine Nachricht empfangen, die von einem Fenster in ein anderes Fenster für die Verarbeitung weiterzuleiten. Die lParam- und WPARAM-Parameter werden wie folgt verwendet:  
  
|Parameter|Verwendung|  
|---------------|-----------|  
|WPARAM-PARAMETER|Daten, die vom Benutzer definiert werden.|  
|LPARAM|Ein Zeiger auf eine `MSG` Struktur, die Informationen zu einer Meldung enthält.|  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel `m_hWndOther` stellt dar, das andere Fenster, das diese Nachricht empfangen hat.  
  
 [!code-cpp[NVC_ATL_Windowing#137](../../atl/codesnippet/cpp/windows-messages-macros_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)
