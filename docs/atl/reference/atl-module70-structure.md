---
title: _ATL_MODULE70-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- _ATL_MODULE70
- ATL::_ATL_MODULE70
- ATL._ATL_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- ATL_MODULE70 structure
- _ATL_MODULE70 structure
ms.assetid: b059b2c8-dfd1-4ac9-b07d-39df638cc7b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f84b90613bcf542a9ace44505565951819fcaa91
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108442"
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

