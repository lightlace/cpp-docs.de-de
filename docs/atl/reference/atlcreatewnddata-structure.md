---
title: _AtlCreateWndData-Struktur
ms.date: 11/04/2016
f1_keywords:
- ATL::_AtlCreateWndData
- ATL._AtlCreateWndData
- _AtlCreateWndData
helpviewer_keywords:
- _AtlCreateWndData structure
- AtlCreateWndData structure
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
ms.openlocfilehash: 860d5772279d0ca0581a8cac1e0ef224f829586d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534185"
---
# <a name="atlcreatewnddata-structure"></a>_AtlCreateWndData-Struktur

Diese Struktur enthält die Daten von Klasseninstanzen Windowing-Code in ATL

## <a name="syntax"></a>Syntax

```
    struct _AtlCreateWndData{
    void* m_pThis;
    DWORD m_dwThreadID;
    _AtlCreateWndData* m_pNext;
};
```

## <a name="members"></a>Member

`m_pThis`<br/>
Die **dies** Zeiger verwendet, um den Zugriff auf die Instanz der Klasse in Fensterprozeduren abzurufen.

`m_dwThreadID`<br/>
Die Thread-ID der aktuellen Klasseninstanz.

`m_pNext`<br/>
Zeiger auf die nächste `_AtlCreateWndData` Objekt.

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

## <a name="see-also"></a>Siehe auch

[Klassen und Strukturen](../../atl/reference/atl-classes.md)

