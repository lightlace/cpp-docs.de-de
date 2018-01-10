---
title: _ATL_WIN_MODULE70 Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _ATL_WIN_MODULE70
- ATL::_ATL_WIN_MODULE70
- ATL._ATL_WIN_MODULE70
dev_langs: C++
helpviewer_keywords:
- _ATL_WIN_MODULE70 structure
- ATL_WIN_MODULE70 structure
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 733808006a3c301972c4ab3b3f8de3320d9fde46
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="atlwinmodule70-structure"></a>_ATL_WIN_MODULE70-Struktur
Verwendet von Windowing Code in ATL  
  
## <a name="syntax"></a>Syntax  
  
```
struct _ATL_WIN_MODULE70 {
    UNIT cbSize; 
    CRITICAL_SECTION m_csWindowCreate;
    _AtlCreateWndData* m_pCreateWndList;
    CSimpleArray<ATOM> m_rgWindowClassAtoms;
};
```  
  
## <a name="members"></a>Member  
 `cbSize`  
 Die Größe der Struktur, die für die versionsverwaltung verwendet.  
  
 `m_csWindowCreate`  
 Verwendet, um die Serialisierung des Zugriffs auf Registrierungscode Fenster. Wird intern vom ATL verwendet  
  
 **m_pCreateWndList**  
 Zum Binden von Windows an ihre Objekte verwendet. Wird intern vom ATL verwendet  
  
 **m_rgWindowClassAtoms**  
 Verwendet, um das Fenster Klasse Registrierungen nachverfolgt werden, damit sie ordnungsgemäß bei Beendigung aufgehoben werden können. Wird intern vom ATL verwendet  
  
## <a name="remarks"></a>Hinweise  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module) ist definiert als Typedef von `_ATL_WIN_MODULE70`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen](../../atl/reference/atl-structures.md)





