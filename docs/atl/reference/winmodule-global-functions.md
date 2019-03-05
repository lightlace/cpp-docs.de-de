---
title: Globale WinModule-Funktionen
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlWinModuleAddCreateWndData
- atlbase/ATL::AtlWinModuleExtractCreateWndData
ms.assetid: 8ce45a5b-26a7-491f-9096-c09ceca5f2c2
ms.openlocfilehash: 0e7450ea2a42c0b35dc5a6d1b77dfb0f2acb9520
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265084"
---
# <a name="winmodule-global-functions"></a>Globale WinModule-Funktionen

Diese Funktionen bieten Unterstützung für `_AtlCreateWndData` Vorgängen zu strukturieren.

> [!IMPORTANT]
> In der folgenden Tabelle aufgeführten Funktionen können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

|||
|-|-|
|[AtlWinModuleAddCreateWndData](#atlwinmoduleaddcreatewnddata)|Mit dieser Funktion wird eine `_AtlCreateWndData`-Struktur initialisiert und hinzugefügt.|
|[AtlWinModuleExtractCreateWndData](#atlwinmoduleextractcreatewnddata)|Mit dieser Funktion wird eine vorhandene `_AtlCreateWndData`-Struktur extrahiert.|

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="atlwinmoduleaddcreatewnddata"></a>  AtlWinModuleAddCreateWndData

Mit dieser Funktion wird eine `_AtlCreateWndData`-Struktur initialisiert und hinzugefügt.

```
ATLINLINE ATLAPI_(void) AtlWinModuleAddCreateWndData(
    _ATL_WIN_MODULE* pWinModule,
    _AtlCreateWndData* pData,
    void* pObject);
```

### <a name="parameters"></a>Parameter

*pWinModule*<br/>
Zeiger auf ein Modul des [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) Struktur.

*pData*<br/>
Zeiger auf die [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) Struktur initialisiert und auf das aktuelle Modul hinzugefügt werden.

*pObject*<br/>
Zeiger auf ein Objekt des **dies** Zeiger.

### <a name="remarks"></a>Hinweise

Initialisiert ein `_AtlCreateWndData` -Struktur, die zum Speichern von der **dies** Zeiger verwendet, um Klasseninstanzen verweisen, und fügt es der Liste auf die verwiesen wird von einem Modul die hinzu `_ATL_WIN_MODULE70` Struktur. Wird aufgerufen, indem [CAtlWinModule::AddCreateWndData](catlwinmodule-class.md#addcreatewnddata).

##  <a name="atlwinmoduleextractcreatewnddata"></a>  AtlWinModuleExtractCreateWndData

Mit dieser Funktion wird eine vorhandene `_AtlCreateWndData`-Struktur extrahiert.

```
ATLINLINE ATLAPI_(void*) AtlWinModuleExtractCreateWndData(_ATL_WIN_MODULE* pWinModule);
```

### <a name="parameters"></a>Parameter

*pWinModule*<br/>
Zeiger auf ein Modul des [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) Struktur.

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) Struktur.

### <a name="remarks"></a>Hinweise

Diese Funktion wird eine vorhandene extrahiert `_AtlCreateWndData` Struktur aus der Liste auf die verwiesen wird von einem Modul die `_ATL_WIN_MODULE70` Struktur.

## <a name="see-also"></a>Siehe auch

[Funktionen](../../atl/reference/atl-functions.md)
