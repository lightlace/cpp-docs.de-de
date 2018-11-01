---
title: _ATL_MODULE70-Struktur
ms.date: 11/04/2016
f1_keywords:
- _ATL_MODULE70
- ATL::_ATL_MODULE70
- ATL._ATL_MODULE70
helpviewer_keywords:
- ATL_MODULE70 structure
- _ATL_MODULE70 structure
ms.assetid: b059b2c8-dfd1-4ac9-b07d-39df638cc7b3
ms.openlocfilehash: bf733a10a0be53eafb634c645dad6a4b58b8206d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438843"
---
# <a name="atlmodule70-structure"></a>_ATL_MODULE70-Struktur

Enthält Daten, die von jedem ATL-Modul verwendet.

## <a name="syntax"></a>Syntax

```
struct _ATL_MODULE70 {
    UINT cbSize;
    LONG m_nLockCnt;
    _ATL_TERMFUNC_ELEM* m_pTermFuncs;
    CComCriticalSection m_csStaticDataInitAndTypeInfo;
};
```

## <a name="members"></a>Member

`cbSize`<br/>
Die Größe der Struktur, die für die versionsverwaltung verwendet werden soll.

`m_nLockCnt`<br/>
Um zu bestimmen, wie lange das Modul aktiv bleiben soll, Verweiszähler dieser Planergruppe.

`m_pTermFuncs`<br/>
Verfolgt-Funktionen, die aufgerufen werden, wenn Sie ATL fährt registriert wurden.

`m_csStaticDataInitAndTypeInfo`<br/>
Verwendet, um den Zugriff auf interne Daten in mehreren Threads Situationen zu koordinieren.

## <a name="remarks"></a>Hinweise

[_ATL_MODULE](atl-typedefs.md#_atl_module) ist definiert als Typedef von `_ATL_MODULE70`.

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

## <a name="see-also"></a>Siehe auch

[Klassen und Strukturen](../../atl/reference/atl-classes.md)

