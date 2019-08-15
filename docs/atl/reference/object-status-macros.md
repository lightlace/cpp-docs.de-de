---
title: Objektstatusmakros
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
ms.openlocfilehash: dc50825d6b6e74dc263a097e86d8ea0d42989825
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495323"
---
# <a name="object-status-macros"></a>Objektstatusmakros

Dieses Makro legt Flags fest, die zu ActiveX-Steuerelementen gehören.

|||
|-|-|
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|Wird in ATL-ActiveX-Steuerelementen zum Festlegen der OLEMISC-Flags verwendet.|

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="declare_olemisc_status"></a>DECLARE_OLEMISC_STATUS

Wird in ATL-ActiveX-Steuerelementen zum Festlegen der OLEMISC-Flags verwendet.

```
DECLARE_OLEMISC_STATUS( miscstatus )
```

### <a name="parameters"></a>Parameter

*miscstatus*<br/>
Alle anwendbaren OLEMISC-Flags.

### <a name="remarks"></a>Hinweise

Dieses Makro wird verwendet, um die OLEMISC-Flags für ein ActiveX-Steuerelement festzulegen. Weitere Informationen finden Sie unter [IOleObject:: getfehlstatus](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) .

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]

## <a name="see-also"></a>Siehe auch

[Makros](../../atl/reference/atl-macros.md)
