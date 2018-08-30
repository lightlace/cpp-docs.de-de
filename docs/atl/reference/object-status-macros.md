---
title: Objekt-Objektstatus-Makros | Microsoft-Dokumentation
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
ms.openlocfilehash: 6fcfffcd9508876399b30238cac0b4f65c92c733
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43206500"
---
# <a name="object-status-macros"></a>Objektstatus-Makros
Dieses Makro legt die Flags, die für ActiveX-Steuerelemente gehören.  
  
|||  
|-|-|  
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|In ATL-ActiveX-Steuerelementen verwendet, werden die OLEMISC-Flags festgelegt.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  

##  <a name="declare_olemisc_status"></a>  DECLARE_OLEMISC_STATUS  
 In ATL-ActiveX-Steuerelementen verwendet, werden die OLEMISC-Flags festgelegt.  
  
```
DECLARE_OLEMISC_STATUS( miscstatus )
```  
  
### <a name="parameters"></a>Parameter  
 *MiscStatus*  
 Alle geltenden OLEMISC-Flags.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro wird verwendet, werden die OLEMISC-Flags für ein ActiveX-Steuerelement festgelegt. Finden Sie unter [IOleObject::GetMiscStatus](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) Weitere Details.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)
