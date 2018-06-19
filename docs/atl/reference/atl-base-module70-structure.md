---
title: _ATL_BASE_MODULE70 Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATL::_ATL_BASE_MODULE70
- ATL._ATL_BASE_MODULE70
- _ATL_BASE_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- ATL_BASE_MODULE70 structure
- _ATL_BASE_MODULE70 structure
ms.assetid: 4539282f-15b8-4d7c-aafa-a85dc56f4980
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 484fc4a68d0421cb12e901b2d56f30e95f6cb79b
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
ms.locfileid: "34256417"
---
# <a name="atlbasemodule70-structure"></a>_ATL_BASE_MODULE70-Struktur
Von jedem Projekt, die ATL verwendet verwendet  
  
## <a name="syntax"></a>Syntax  
  
```
struct _ATL_BASE_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInst;
    HINSTANCE m_hInstResource;
    bool m_bNT5orWin98;
    DWORD dwAtlBuildVer;
    GUID* pguidVer;
    CRITICAL_SECTION m_csResource;
    CSimpleArray<HINSTANCE> m_rgResourceInstance;
};
```  
  
## <a name="members"></a>Member  
 `cbSize`  
 Die Größe der Struktur, die für die versionsverwaltung verwendet.  
  
 `m_hInst`  
 Die **hInstance** für dieses Modul (Exe oder Dll).  
  
 `m_hInstResource`  
 Ressourcenhandle für Standard-Instanz.  
  
 **m_bNT5orWin98**  
 Informationen zur Betriebssystemversion. Wird intern vom ATL verwendet  
  
 **dwAtlBuildVer**  
 Speichert die Version von ATL Derzeit 0x0700.  
  
 **pguidVer**  
 Interne des ATL-GUID.  
  
 **m_csResource**  
 Zum Synchronisieren des Zugriffs auf die **M_rgResourceInstance** Array. Wird intern vom ATL verwendet  
  
 **m_rgResourceInstance**  
 Array verwendet, um die Suche nach Ressourcen in der Ressourceninstanzen der ATL fähig ist. Wird intern vom ATL verwendet  
  
## <a name="remarks"></a>Hinweise  
 [_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module) ist definiert als Typedef von `_ATL_BASE_MODULE70`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcore.h  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen und Strukturen](../../atl/reference/atl-classes.md)





