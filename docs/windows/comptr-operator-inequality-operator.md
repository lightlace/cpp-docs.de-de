---
title: Comptr::! =-Operator | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator!=
dev_langs:
- C++
ms.assetid: 63647240-dec7-4eb9-9272-96c07d01493c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4874121f22daa8e4a13bf7a1d332c9b8e3db60ba
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42578106"
---
# <a name="comptroperator-operator"></a>ComPtr::operator!=-Operator

Gibt an, ob zwei **ComPtr** -Objekte ungleich sind.

## <a name="syntax"></a>Syntax

```cpp
bool operator!=(
   const ComPtr<T>& a,
   const ComPtr<U>& b
);

bool operator!=(
   const ComPtr<T>& a,
   decltype(__nullptr)  
);

bool operator!=(
   decltype(__nullptr),
   const ComPtr<T>& a
);
```

### <a name="parameters"></a>Parameter

*a*  
Ein Verweis auf eine **ComPtr** Objekt.

*b*  
Ein Verweis auf einen anderen **ComPtr** Objekt.

## <a name="return-value"></a>Rückgabewert

Der erste Operator ergibt **"true"** Wenn Objekt *eine* ist nicht gleich Objekt *b*ist, andernfalls **"false"**.

Führen Sie die zweite und dritte Operator **"true"** Wenn Objekt *eine* ist nicht gleich **"nullptr"** ist, andernfalls **"false"**.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)  
[ComPtr-Klasse](../windows/comptr-class.md)