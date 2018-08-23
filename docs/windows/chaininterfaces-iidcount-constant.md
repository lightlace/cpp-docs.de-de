---
title: 'Chaininterfaces:: Iidcount-Konstante | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::IidCount
dev_langs:
- C++
helpviewer_keywords:
- IidCount constant
ms.assetid: d4a90aa0-513c-4e99-b978-e12149734936
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a97ea483bddb0ed6b2fadce1f9daa50eab82591a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42596904"
---
# <a name="chaininterfacesiidcount-constant"></a>ChainInterfaces::IidCount-Konstante

Die Gesamtanzahl der Schnittstellen-IDs enthalten, die in den Schnittstellen, die vom Vorlagenparameter angegeben *I0* über *I9*.

## <a name="syntax"></a>Syntax

```cpp
static const unsigned long IidCount = Details::InterfaceTraits<I0>::IidCount + Details::InterfaceTraits<I1>::IidCount + Details::InterfaceTraits<I2>::IidCount + Details::InterfaceTraits<I3>::IidCount + Details::InterfaceTraits<I4>::IidCount + Details::InterfaceTraits<I5>::IidCount + Details::InterfaceTraits<I6>::IidCount + Details::InterfaceTraits<I7>::IidCount + Details::InterfaceTraits<I8>::IidCount + Details::InterfaceTraits<I9>::IidCount;
```

## <a name="return-value"></a>Rückgabewert

Die Gesamtanzahl der Schnittstellen-IDs.

## <a name="remarks"></a>Hinweise

Vorlagenparameter *I0* und *I1* sind erforderlich, und die Parameter *I2* über *I9* sind optional. Die Anzahl der IID jeder Schnittstelle ist in der Regel 1.

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[ChainInterfaces-Struktur](../windows/chaininterfaces-structure.md)