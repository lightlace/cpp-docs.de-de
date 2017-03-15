---
title: Windows-Nachrichten Makros | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
caps.latest.revision: 16
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: be814c0a2ade7df8f7a4d6863627e79efe0a48bc
ms.lasthandoff: 02/24/2017

---
# <a name="windows-messages-macros"></a>Windows-Nachrichten Makros
Dieses Makro leitet Windows-Meldungen.  
  
|||  
|-|-|  
|[WM_FORWARDMSG](#wm_forwardmsg)|Verwenden Sie eine Nachricht empfangen, die von einem Fenster in ein anderes Fenster zur Verarbeitung weitergeleitet.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h 
   
##  <a name="a-namewmforwardmsga--wmforwardmsg"></a><a name="wm_forwardmsg"></a>WM_FORWARDMSG  
 Dieses Makro leitet eine Nachricht von einem Fenster in ein anderes Fenster für die Verarbeitung empfangen.  
  
```
WM_FORWARDMSG
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Meldung verarbeitet wurde,&0;, falls nicht.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `WM_FORWARDMSG` eine Nachricht empfangen, die von einem Fenster in ein anderes Fenster zur Verarbeitung weitergeleitet. Der Parameter LPARAM und WPARAM-Parameter werden wie folgt verwendet:  
  
|Parameter|Verwendung|  
|---------------|-----------|  
|WPARAM|Daten, die vom Benutzer definiert werden.|  
|LPARAM|Ein Zeiger auf eine `MSG` -Struktur, die Informationen über eine Nachricht enthält.|  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel `m_hWndOther` die anderen Fenster darstellt, das diese Nachricht empfangen hat.  
  
 [!code-cpp[NVC_ATL_Windowing&#137;](../../atl/codesnippet/cpp/windows-messages-macros_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)

