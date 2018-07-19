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
ms.openlocfilehash: 9666d73eec770ff8231e5730e01520b0bee68012
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37886218"
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
 `cbSize`  
 Die Größe der Struktur, die für die versionsverwaltung verwendet werden soll.  
  
 `m_nLockCnt`  
 Um zu bestimmen, wie lange das Modul aktiv bleiben soll, Verweiszähler dieser Planergruppe.  
  
 `m_pTermFuncs`  
 Verfolgt-Funktionen, die aufgerufen werden, wenn Sie ATL fährt registriert wurden.  
  
 `m_csStaticDataInitAndTypeInfo`  
 Verwendet, um den Zugriff auf interne Daten in mehreren Threads Situationen zu koordinieren.  
  
## <a name="remarks"></a>Hinweise  
 [_ATL_MODULE](atl-typedefs.md#_atl_module) ist definiert als Typedef von `_ATL_MODULE70`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
## <a name="see-also"></a>Siehe auch  
  [Klassen und Strukturen](../../atl/reference/atl-classes.md)







