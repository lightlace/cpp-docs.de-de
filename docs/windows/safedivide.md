---
title: SafeDivide | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeDivide
dev_langs:
- C++
helpviewer_keywords:
- SafeDivide function
ms.assetid: b5b27484-ad6e-46b1-ba9f-1c7120dd103b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 98f37a428c81276788ea4aef315e7266a9da02c4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383401"
---
# <a name="safedivide"></a>SafeDivide

Dividiert zwei Zahlen in einer Weise, die Division durch 0 (null) schützt.

## <a name="syntax"></a>Syntax

```cpp
template<typename T, typename U>
inline bool SafeDivide (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Parameter

*t*<br/>
[in] Der Divisor. Dies muss vom Typ "t".

*u*<br/>
[in] Der Dividend. Dies muss u sein.

*Ergebnis*<br/>
[out] Der Parameter, in denen **SafeDivide** speichert das Ergebnis.

## <a name="return-value"></a>Rückgabewert

**"true"** Wenn kein Fehler auftritt. **"false"** Wenn ein Fehler auftritt.

## <a name="remarks"></a>Hinweise

Diese Methode ist Teil des [SafeInt-Bibliothek](../windows/safeint-library.md) und ist ohne eine Instanz des für einen einzelnen Unterteilung-Vorgang für die [SafeInt-Klasse](../windows/safeint-class.md).

> [!NOTE]
> Diese Methode sollte nur verwendet werden, wenn eine einzelne mathematische Operation, die geschützt werden muss. Wenn mehrere Vorgänge vorhanden sind, sollten Sie verwenden die `SafeInt` Klasse anstelle von den einzelnen eigenständigen Funktionen.

Weitere Informationen zu den Vorlagentypen T "und" U, finden Sie unter [SafeInt-Funktionen](../windows/safeint-functions.md).

## <a name="requirements"></a>Anforderungen

**Header:** safeint.h

**Namespace:** Microsoft::Utilities

## <a name="see-also"></a>Siehe auch

[SafeInt-Funktionen](../windows/safeint-functions.md)<br/>
[SafeInt-Bibliothek](../windows/safeint-library.md)<br/>
[SafeInt-Klasse](../windows/safeint-class.md)<br/>
[SafeModulus](../windows/safemodulus.md)<br/>
[SafeMultiply](../windows/safemultiply.md)