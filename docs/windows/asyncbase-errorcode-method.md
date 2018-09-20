---
title: 'Asyncbase:: ErrorCode-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::ErrorCode
dev_langs:
- C++
helpviewer_keywords:
- ErrorCode method
ms.assetid: 3f5f0f69-d60a-4a67-8cc6-a55fdc89a192
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8da9da0ffbfb8291082f7f600ca72bf1937c3bfc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46435544"
---
# <a name="asyncbaseerrorcode-method"></a>AsyncBase::ErrorCode-Methode

Ruft den Fehlercode für den aktuellen asynchronen Vorgang ab.

## <a name="syntax"></a>Syntax

```cpp
inline void ErrorCode(
   HRESULT *error
);
```

### <a name="parameters"></a>Parameter

*Fehler*<br/>
Der Speicherort, in dem dieser Vorgang den Fehlercode der aktuellen speichert.

## <a name="remarks"></a>Hinweise

Dieser Vorgang ist threadsicher.

## <a name="requirements"></a>Anforderungen

**Header:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[AsyncBase-Klasse](../windows/asyncbase-class.md)