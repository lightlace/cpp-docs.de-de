---
title: GetModuleBase-Funktion
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::GetModuleBase
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
ms.openlocfilehash: 40289903eba2ce7ac35d4d0b208c3b609efb09f2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50650813"
---
# <a name="getmodulebase-function"></a>GetModuleBase-Funktion
Ruft eine [ModuleBase](../windows/modulebase-class.md) Zeiger, der inkrementiert und dekrementiert den Verweiszähler des ermöglicht eine [RuntimeClass](../windows/runtimeclass-class.md) Objekt.

## <a name="syntax"></a>Syntax

```cpp
inline Details::ModuleBase* GetModuleBase() throw()
```

## <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein `ModuleBase` -Objekt.

## <a name="remarks"></a>Hinweise

Diese Funktion wird intern zum Inkrementieren und Dekrementieren verwendet Verweiszähler des Objekts.

Sie können diese Funktion verwenden, zum Steuern der Verweiszähler durch Aufrufen von [modulebase:: Incrementobjectcount](../windows/modulebase-incrementobjectcount-method.md) und [modulebase:: Decrementobjectcount](../windows/modulebase-decrementobjectcount-method.md).

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)