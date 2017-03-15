---
title: _ATL_MODULE70 Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 4e393abb2a904a0f5e101efe3d78d0645664397b
ms.openlocfilehash: ea1d87d3d500fc08f3da16de6820ca003e899419
ms.lasthandoff: 02/24/2017

---
# <a name="atlmodule70-structure"></a>_ATL_MODULE70-Struktur
Enthält Daten, die von jedem ATL verwendet wird.  
  
## <a name="syntax"></a>Syntax  
  
```
struct _ATL_MODULE70 {
    UINT cbSize;
    LONG m_nLockCnt;
    _ATL_TERMFUNC_ELEM* m_pTermFuncs;
    CComCriticalSection m_csStaticDataInitAndTypeInfo;
};
```  
  
## <a name="members"></a>Mitglieder  
 `cbSize`  
 Die Größe der Struktur, die für die Versionskontrolle verwendet.  
  
 `m_nLockCnt`  
 Verweiszähler um zu bestimmen, wie lange das Modul aktiv bleiben soll.  
  
 **m_pTermFuncs**  
 Titel-Funktionen, die aufgerufen werden, wenn ATL heruntergefahren registriert wurden.  
  
 **m_csStaticDataInitAndTypeInfo**  
 Verwendet, um Zugriff auf interne Daten in mehreren Threads Situationen zu koordinieren.  
  
## <a name="remarks"></a>Hinweise  
 [_ATL_MODULE](atl-typedefs.md#_atl_module) ist definiert als Typedef von `_ATL_MODULE70`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen](../../atl/reference/atl-structures.md)








