---
title: _ATL_BASE_MODULE70-Struktur
ms.date: 11/04/2016
f1_keywords:
- ATL::_ATL_BASE_MODULE70
- ATL._ATL_BASE_MODULE70
- _ATL_BASE_MODULE70
helpviewer_keywords:
- ATL_BASE_MODULE70 structure
- _ATL_BASE_MODULE70 structure
ms.assetid: 4539282f-15b8-4d7c-aafa-a85dc56f4980
ms.openlocfilehash: 4fddd4b3af6155d0663b9c01edfab4fcf4a60426
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261453"
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

`cbSize`<br/>
Die Größe der Struktur, die für die versionsverwaltung verwendet werden soll.

`m_hInst`<br/>
Die `hInstance` für dieses Modul (Exe oder Dll).

`m_hInstResource`<br/>
Ressourcenhandle für Standard-Instanz.

`m_bNT5orWin98`<br/>
Versionsinformationen zum Betriebssystem. Wird intern verwendet, von ATL

`dwAtlBuildVer`<br/>
Speichert die Version von ATL Derzeit 0x0700.

`pguidVer`<br/>
Interne des ATL-GUID.

`m_csResource`<br/>
Zum Synchronisieren des Zugriffs auf die `m_rgResourceInstance` Array. Wird intern verwendet, von ATL

`m_rgResourceInstance`<br/>
Das Array verwendet, um die Suche nach Ressourcen in allen Ressourceninstanzen die ATL fähig ist. Wird intern verwendet, von ATL

## <a name="remarks"></a>Hinweise

[_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module) als Typdefinition von _ATL_BASE_MODULE70 definiert ist.

## <a name="requirements"></a>Anforderungen

**Header:** atlcore.h

## <a name="see-also"></a>Siehe auch

[Klassen und Strukturen](../../atl/reference/atl-classes.md)
