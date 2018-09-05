---
title: _AtlCreateWndData-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATL::_AtlCreateWndData
- ATL._AtlCreateWndData
- _AtlCreateWndData
dev_langs:
- C++
helpviewer_keywords:
- _AtlCreateWndData structure
- AtlCreateWndData structure
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c5751fa3c5c8bc20f287ca3c48d885fc41c60ba0
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43764328"
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

`m_pThis`  
Die **dies** Zeiger verwendet, um den Zugriff auf die Instanz der Klasse in Fensterprozeduren abzurufen.

`m_dwThreadID`  
Die Thread-ID der aktuellen Klasseninstanz.

`m_pNext`  
Zeiger auf die nächste `_AtlCreateWndData` Objekt.

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

## <a name="see-also"></a>Siehe auch

[Klassen und Strukturen](../../atl/reference/atl-classes.md)

