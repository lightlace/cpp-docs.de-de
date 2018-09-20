---
title: Comptrref::! =-Operator | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator!=
dev_langs:
- C++
ms.assetid: ab3093cc-6fbd-4039-890a-6df1cde992b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0f4aeb3bc5b2ee0598cf9e7d3f572f1f0e5fb5f2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393177"
---
# <a name="comptrrefoperator-operator"></a>ComPtrRef::operator!=-Operator

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   const Details::ComPtrRef<ComPtr<U>>& b
);

bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   decltype(__nullptr)  
);

bool operator!=(
   decltype(__nullptr),
   const Details::ComPtrRef<ComPtr<T>>& a
);

bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   void* b
);

bool operator!=(
   void* b,
   const Details::ComPtrRef<ComPtr<T>>& a
);
```

### <a name="parameters"></a>Parameter

*a*<br/>
Ein Verweis auf eine **ComPtrRef** Objekt.

*b*<br/>
Ein Verweis auf einen anderen **ComPtrRef** Objekt oder ein Zeiger auf ein anonymes Objekt (`void*`).

## <a name="return-value"></a>Rückgabewert

Der erste Operator ergibt **"true"** Wenn Objekt *eine* ist nicht gleich Objekt *b*ist, andernfalls **"false"**.

Führen Sie die zweite und dritte Operator **"true"** Wenn Objekt *eine* ist nicht gleich **"nullptr"** ist, andernfalls **"false"**.

Die vierten und fünften-Operatoren ergeben **"true"** Wenn Objekt *eine* ist nicht gleich Objekt *b*ist, andernfalls **"false"**.

## <a name="remarks"></a>Hinweise

Gibt an, ob zwei **ComPtrRef** -Objekte ungleich sind.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)<br/>
[ComPtrRef-Klasse](../windows/comptrref-class.md)