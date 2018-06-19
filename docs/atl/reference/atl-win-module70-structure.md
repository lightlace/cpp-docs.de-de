---
title: _ATL_WIN_MODULE70 Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- _ATL_WIN_MODULE70
- ATL::_ATL_WIN_MODULE70
- ATL._ATL_WIN_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- _ATL_WIN_MODULE70 structure
- ATL_WIN_MODULE70 structure
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 587b115c428b0d82183abbec9f712ff06ea448f4
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
ms.locfileid: "34256079"
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
 [Klassen und Strukturen](../../atl/reference/atl-classes.md)





