---
title: SafeMultiply | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeMultiply
dev_langs:
- C++
helpviewer_keywords:
- SafeMultiply function
ms.assetid: 81d988a5-fac7-4930-8c37-c24fa8e2c853
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 003f2c9241a4ba81e370204ce2102b60e420df04
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700543"
---
# <a name="safemultiply"></a>SafeMultiply

Multipliziert zwei Zahlen in einer Weise, die schützt vor Ganzzahlüberlauf zusammen.

## <a name="syntax"></a>Syntax

```cpp
template<typename T, typename U>
inline bool SafeMultiply (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Parameter

*t*<br/>
[in] Die erste zu multiplizierende Zahl. Dies muss vom Typ `T`.

*u*<br/>
[in] Die zweite zu multiplizierende Zahl. Dies muss vom Typ `U`.

*Ergebnis*<br/>
[out] Der Parameter, in denen **SafeMultiply** speichert das Ergebnis.

## <a name="return-value"></a>Rückgabewert

**"true"** Wenn kein Fehler auftritt. **"false"** Wenn ein Fehler auftritt.

## <a name="remarks"></a>Hinweise

Diese Methode ist Teil des [SafeInt-Bibliothek](../windows/safeint-library.md) und ist für eine einzelne Multiplikation ohne eine Instanz des für die [SafeInt-Klasse](../windows/safeint-class.md).

> [!NOTE]
> Diese Methode sollte nur verwendet werden, wenn eine einzelne mathematische Operation, die geschützt werden muss. Wenn mehrere Vorgänge vorhanden sind, sollten Sie verwenden die `SafeInt` Klasse anstelle von den einzelnen eigenständigen Funktionen.

Weitere Informationen zu den Vorlagentypen `T` und `U`, finden Sie unter [SafeInt-Funktionen](../windows/safeint-functions.md).

## <a name="requirements"></a>Anforderungen

**Header:** safeint.h

**Namespace:** Microsoft::Utilities

## <a name="see-also"></a>Siehe auch

[SafeInt-Funktionen](../windows/safeint-functions.md)  
[SafeInt-Bibliothek](../windows/safeint-library.md)  
[SafeInt-Klasse](../windows/safeint-class.md)  
[SafeDivide](../windows/safedivide.md)