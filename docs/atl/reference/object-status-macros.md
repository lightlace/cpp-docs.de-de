---
title: Objektstatus-Makros
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
ms.openlocfilehash: 9c4df80b2b9828077ec3738bc296f19aadf2df68
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658951"
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

*MiscStatus*<br/>
Alle geltenden OLEMISC-Flags.

### <a name="remarks"></a>Hinweise

Dieses Makro wird verwendet, werden die OLEMISC-Flags für ein ActiveX-Steuerelement festgelegt. Finden Sie unter [IOleObject::GetMiscStatus](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) Weitere Details.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]

## <a name="see-also"></a>Siehe auch

[Makros](../../atl/reference/atl-macros.md)
