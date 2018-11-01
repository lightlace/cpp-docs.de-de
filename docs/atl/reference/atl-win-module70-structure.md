---
title: _ATL_WIN_MODULE70-Struktur
ms.date: 11/04/2016
f1_keywords:
- _ATL_WIN_MODULE70
- ATL::_ATL_WIN_MODULE70
- ATL._ATL_WIN_MODULE70
helpviewer_keywords:
- _ATL_WIN_MODULE70 structure
- ATL_WIN_MODULE70 structure
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
ms.openlocfilehash: 4f1718c76d21f2e13b36c29db785fe989ff6108e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482516"
---
# <a name="atlwinmodule70-structure"></a>_ATL_WIN_MODULE70-Struktur

Windowing-Code in ATL verwendet

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

`cbSize`<br/>
Die Größe der Struktur, die für die versionsverwaltung verwendet werden soll.

`m_csWindowCreate`<br/>
Verwendet, um die Serialisierung des Zugriffs auf Fenster-Registrierungscode. Wird intern verwendet, von ATL

`m_pCreateWndList`<br/>
Zum Binden von Windows in ihre Objekte verwendet. Wird intern verwendet, von ATL

`m_rgWindowClassAtoms`<br/>
Verwendet, um die Registrierungen für Fenster-Klasse nachverfolgt, damit sie ordnungsgemäß bei Beendigung des aufgehoben werden können. Wird intern verwendet, von ATL

## <a name="remarks"></a>Hinweise

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module) ist definiert als Typedef von `_ATL_WIN_MODULE70`.

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

## <a name="see-also"></a>Siehe auch

[Klassen und Strukturen](../../atl/reference/atl-classes.md)

