---
title: Objekt-Status-Makros | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
dev_langs:
- C++
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eddfc28c659d0c1eb54794d8fc76a9f3a4f9e73b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360873"
---
# <a name="object-status-macros"></a>Status-Makros
Dieses Makro legt Flags, die für ActiveX-Steuerelemente gehören.  
  
|||  
|-|-|  
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|In ATL-ActiveX-Steuerelemente verwendet, um das Festlegen der **OLEMISC** Flags.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  

##  <a name="declare_olemisc_status"></a>  DECLARE_OLEMISC_STATUS  
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
