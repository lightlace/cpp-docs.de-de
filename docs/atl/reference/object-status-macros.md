---
title: Objektstatus-Makros
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
ms.openlocfilehash: cb5ff6d7570b03b32852fc450f58043446f721f4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62198173"
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

*miscstatus*<br/>
Alle geltenden OLEMISC-Flags.

### <a name="remarks"></a>Hinweise

Dieses Makro wird verwendet, werden die OLEMISC-Flags für ein ActiveX-Steuerelement festgelegt. Finden Sie unter [IOleObject::GetMiscStatus](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) Weitere Details.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]

## <a name="see-also"></a>Siehe auch

[Makros](../../atl/reference/atl-macros.md)
