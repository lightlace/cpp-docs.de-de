---
title: 'Comptrref:: Operator ==-Operator | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator==
dev_langs:
- C++
ms.assetid: 95fcf781-b473-4317-88cd-e938778d3c3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: abf78644f7cad90d25d365f6237407aeaeb6917b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42575702"
---
# <a name="comptrrefoperator-operator"></a>ComPtrRef::operator==-Operator

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   const Details::ComPtrRef<ComPtr<U>>& b
);

bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   decltype(__nullptr)  
);

bool operator==(
   decltype(__nullptr),
   const Details::ComPtrRef<ComPtr<T>>& a
);

bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   void* b
);

bool operator==(
   void* b,
   const Details::ComPtrRef<ComPtr<T>>& a
);
```

### <a name="parameters"></a>Parameter

*a*  
Ein Verweis auf eine **ComPtrRef** Objekt.

*b*  
Ein Verweis auf einen anderen **ComPtrRef** Objekt oder ein Zeiger auf einen anonymen Typ (`void*`).

## <a name="return-value"></a>Rückgabewert

Der erste Operator ergibt **"true"** Wenn Objekt *eine* Objekt entspricht *b*ist, andernfalls **"false"**.

Führen Sie die zweite und dritte Operator **"true"** Wenn Objekt *eine* gleich **"nullptr"** ist, andernfalls **"false"**.

Die vierten und fünften-Operatoren ergeben **"true"** Wenn Objekt *eine* Objekt entspricht *b*ist, andernfalls **"false"**.

## <a name="remarks"></a>Hinweise

Gibt an, ob zwei **ComPtrRef** Objekte gleich sind.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)  
[ComPtrRef-Klasse](../windows/comptrref-class.md)