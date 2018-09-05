---
title: _ATL_BASE_MODULE70-Struktur | Microsoft-Dokumentation
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
ms.openlocfilehash: fb7218d7fc8886cffdcce13f09a682fdc635f84f
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43759927"
---
# <a name="atlbasemodule70-structure"></a>_ATL_BASE_MODULE70-Struktur

Ein, die Projekte, die ATL verwendet.

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
Die Größe der Struktur, die für die versionsverwaltung verwendet werden soll.

`m_hInst`  
Die `hInstance` für dieses Modul (Exe oder Dll).

`m_hInstResource`  
Ressourcenhandle für Standard-Instanz.

`m_bNT5orWin98`  
Versionsinformationen zum Betriebssystem. Wird intern verwendet, von ATL

`dwAtlBuildVer`  
Speichert die Version von ATL Derzeit 0x0700.

`pguidVer`  
Interne des ATL-GUID.

`m_csResource`  
Zum Synchronisieren des Zugriffs auf die `m_rgResourceInstance` Array. Wird intern verwendet, von ATL

`m_rgResourceInstance`  
Das Array verwendet, um die Suche nach Ressourcen in allen Ressourceninstanzen die ATL fähig ist. Wird intern verwendet, von ATL

## <a name="remarks"></a>Hinweise

[_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module) als Typdefinition von _ATL_BASE_MODULE70 definiert ist.

## <a name="requirements"></a>Anforderungen

**Header:** atlcore.h

## <a name="see-also"></a>Siehe auch

[Klassen und Strukturen](../../atl/reference/atl-classes.md)

