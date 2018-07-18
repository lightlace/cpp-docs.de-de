---
title: alignment_of-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::alignment_of
dev_langs:
- C++
helpviewer_keywords:
- alignment_of class
- alignment_of
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b679d4c8807a19c977cd7e59481dc1d78e67ba1
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956517"
---
# <a name="alignmentof-class"></a>alignment_of-Klasse

Ruft die Ausrichtung des angegebenen Typs ab. Diese Struktur wird in Bezug auf [alignof](../cpp/alignof-and-alignas-cpp.md) implementiert. Verwenden Sie `alignof` direkt, wenn Sie einen Ausrichtungswert einfach abfragen müssen. Verwenden Sie „alignment_of“, wenn Sie eine integrale Konstante benötigen, beispielsweise beim Versenden eines Tags.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct alignment_of;
```

### <a name="parameters"></a>Parameter

*Ty* der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Die Typabfrage enthält den Wert der die Ausrichtung des Typs *Ty*.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[aligned_storage-Klasse](../standard-library/aligned-storage-class.md)<br/>
