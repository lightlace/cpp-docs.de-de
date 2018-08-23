---
title: 'Weakref:: CopyTo-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::CopyTo
dev_langs:
- C++
helpviewer_keywords:
- CopyTo method
ms.assetid: f83de6da-b3d4-41a6-9845-cd725ecf3b75
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 791e9040d9e35c7dfb657cca38e26c01e86c86c4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42594420"
---
# <a name="weakrefcopyto-method"></a>WeakRef::CopyTo-Methode

Weist einer Schnittstelle einen Zeiger zu, falls verfügbar zur angegebenen Zeigervariablen.

## <a name="syntax"></a>Syntax

```cpp
HRESULT CopyTo(
   REFIID riid,
   _Deref_out_ IInspectable** ptr
);

template<typename U>
HRESULT CopyTo(
   _Deref_out_ U** ptr
);

HRESULT CopyTo(
   _Deref_out_ IWeakReference** ptr
);
```

### <a name="parameters"></a>Parameter

*U*  
Zeiger ein `IInspectable` Schnittstelle. Ein Fehler wird ausgegeben, wenn *U* stammt nicht aus `IInspectable`.

*riid*  
Eine Schnittstellen-ID. Ein Fehler wird ausgegeben, wenn *Riid* stammt nicht aus `IWeakReference`.

*ptr*  
Ein doppelt indirekter Zeiger auf `IInspectable` oder `IWeakReference`.

## <a name="return-value"></a>Rückgabewert

„S_OK“ im Erfolgsfall, andernfalls ein HRESULT, das den Fehler beschreibt. Weitere Informationen finden Sie in den **Hinweisen**.

## <a name="remarks"></a>Hinweise

Der Rückgabewert „S_OK“ bedeutet, dass dieser Vorgang erfolgreich war, gibt aber nicht an, ob der schwache Verweis zu einem starken Verweis aufgelöst wurde. Wenn S_OK zurückgegeben wird, testen Sie diesen Parameter *p* ein starker Verweis, d. h. Parameter *p* ist kein **"nullptr"**.

Ab Windows 10-SDKS können dieser Methode ist nicht festgelegt der **WeakRef** Instanz **"nullptr"** Wenn der schwache Verweis nicht abgerufen werden kann, so vermeiden Sie Fehler beim Überprüfen von Code, der WeakRef überprüft. **"nullptr"**. Überprüfen Sie stattdessen *Ptr* für **"nullptr"**.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[WeakRef-Klasse](../windows/weakref-class.md)