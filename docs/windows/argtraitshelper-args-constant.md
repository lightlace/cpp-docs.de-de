---
title: 'Argtraitshelper:: args-Konstante | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraitsHelper::args
dev_langs:
- C++
helpviewer_keywords:
- args constant
ms.assetid: 1c0efa32-c072-43e3-bbd9-a3f6aec069a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6a9b9239d7a75f17915c19e484ad25e0b230834d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46395809"
---
# <a name="argtraitshelperargs-constant"></a>ArgTraitsHelper::args-Konstante

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
static const int args = Traits::args;
```

## <a name="remarks"></a>Hinweise

Hilft [argtraitshelper:: args](../windows/argtraitshelper-args-constant.md) behalten Sie die Anzahl der Parameter der `Invoke` Methode einer Schnittstelle des Delegaten.

## <a name="requirements"></a>Anforderungen

**Header:** event.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[ArgTraitsHelper-Struktur](../windows/argtraitshelper-structure.md)<br/>
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)