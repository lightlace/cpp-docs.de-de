---
title: 'Isbaseofstrict:: value-Konstante | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict::value
dev_langs:
- C++
helpviewer_keywords:
- value constant
ms.assetid: 4a0cdab0-ba03-482b-babf-eeec519ba687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e7159e75b03c6440dfc5742de9f98d93da47d904
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42583853"
---
# <a name="isbaseofstrictvalue-constant"></a>IsBaseOfStrict::value-Konstante

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
static const bool value = __is_base_of(Base, Derived);
```

## <a name="remarks"></a>Hinweise

Gibt an, ob ein Typ die Basis eines anderen ist.

**Wert** ist **"true"** Wenn Typ `Base` ist eine Basisklasse des Typs `Derived`, ansonsten ist der **"false"**.

## <a name="requirements"></a>Anforderungen

**Header:** internal.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[IsBaseOfStrict-Struktur](../windows/isbaseofstrict-structure.md)  
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)