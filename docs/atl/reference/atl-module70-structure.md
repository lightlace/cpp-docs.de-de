---
title: _ATL_MODULE70 Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _ATL_MODULE70
- ATL::_ATL_MODULE70
- ATL._ATL_MODULE70
dev_langs: C++
helpviewer_keywords:
- ATL_MODULE70 structure
- _ATL_MODULE70 structure
ms.assetid: b059b2c8-dfd1-4ac9-b07d-39df638cc7b3
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c8122f733282fa819c3d789a90e60171ee006e27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
 Die Größe der Struktur, die für die versionsverwaltung verwendet.  
  
 `m_nLockCnt`  
 Verweiszähler um zu bestimmen, wie lange das Modul aktiv bleiben sollen.  
  
 **m_pTermFuncs**  
 Verfolgt-Funktionen, die aufgerufen werden, wenn Sie ATL fährt registriert wurden.  
  
 **m_csStaticDataInitAndTypeInfo**  
 Verwendet, um den Zugriff auf interne Daten in mehreren Threads Situationen zu koordinieren.  
  
## <a name="remarks"></a>Hinweise  
 [_ATL_MODULE](atl-typedefs.md#_atl_module) ist definiert als Typedef von `_ATL_MODULE70`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen](../../atl/reference/atl-structures.md)







