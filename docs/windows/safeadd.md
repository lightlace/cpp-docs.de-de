---
title: SafeAdd | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeAdd
dev_langs:
- C++
helpviewer_keywords:
- SafeAdd function
ms.assetid: 3f82b91d-59fe-4ee1-873b-d056182fa8be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2ddf4f69c3c897c8f462554ce6a9db6b2a03408f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400580"
---
# <a name="safeadd"></a>SafeAdd

Addiert zwei Zahlen in einer Weise, die schützt vor Ganzzahlüberlauf an.

## <a name="syntax"></a>Syntax

```cpp
template<typename T, typename U>
inline bool SafeAdd (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Parameter

*t*<br/>
[in] Die erste zu addierende Zahl. Dies muss vom Typ "t".

*u*<br/>
[in] Die zweite zu addierende Zahl. Dies muss u sein.

*Ergebnis*<br/>
[out] Der Parameter, in denen **SafeAdd** speichert das Ergebnis.

## <a name="return-value"></a>Rückgabewert

**"true"** Wenn kein Fehler auftritt. **"false"** Wenn ein Fehler auftritt.

## <a name="remarks"></a>Hinweise

Diese Methode ist Teil des [SafeInt-Bibliothek](../windows/safeint-library.md) und ist für eine einzelne Hinzufügung Vorgang ohne eine Instanz des für die [SafeInt-Klasse](../windows/safeint-class.md).

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
[SafeSubtract](../windows/safesubtract.md)