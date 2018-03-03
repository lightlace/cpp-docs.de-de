---
title: Objekt-Status-Makros | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
dev_langs:
- C++
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1139c30fa5d23f3320cef76d09fb5bd86c8c4bc6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="object-status-macros"></a>Status-Makros
Dieses Makro legt Flags, die für ActiveX-Steuerelemente gehören.  
  
|||  
|-|-|  
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|In ATL-ActiveX-Steuerelemente verwendet, um das Festlegen der **OLEMISC** Flags.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  

##  <a name="declare_olemisc_status"></a>DECLARE_OLEMISC_STATUS  
 Bei ATL-ActiveX-Steuerelemente verwendet, die OLEMISC Flags festgelegt.  
  
```
DECLARE_OLEMISC_STATUS( miscstatus )
```  
  
### <a name="parameters"></a>Parameter  
 *MiscStatus*  
 Alle geltenden OLEMISC-Flags.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro wird verwendet, die OLEMISC-Flags für ein ActiveX-Steuerelement festlegen. Verweisen auf [IOleObject::GetMiscStatus](http://msdn.microsoft.com/library/windows/desktop/ms678521) Weitere Details.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)
