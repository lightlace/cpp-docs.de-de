---
title: SafeCast | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeCast
dev_langs:
- C++
helpviewer_keywords:
- SafeCast function
ms.assetid: 55316729-8456-403a-9f96-59d4038f67af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 65794dafe5e45cbd4c0e2a7eb49c34377009deee
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392982"
---
# <a name="safecast"></a>SafeCast

Wandelt einen Typ der Zahl in einen anderen Typ.

## <a name="syntax"></a>Syntax

```cpp
template<typename T, typename U>
inline bool SafeCast (
   const T From,
   U& To
);
```

### <a name="parameters"></a>Parameter

*From*<br/>
[in] Die Quelle zu konvertierende Zahl. Dies muss vom Typ `T`.

*Aktion*<br/>
[out] Ein Verweis auf die neue Zahlentyp. Dies muss vom Typ `U`.

## <a name="return-value"></a>Rückgabewert

**"true"** Wenn kein Fehler auftritt. **"false"** Wenn ein Fehler auftritt.

## <a name="remarks"></a>Hinweise

Diese Methode ist Teil des [SafeInt-Bibliothek](../windows/safeint-library.md) und ist für eine einzelne Umwandlungsoperation ohne eine Instanz des für die [SafeInt-Klasse](../windows/safeint-class.md).

> [!NOTE]
> Diese Methode sollte nur verwendet werden, wenn Sie ein einzelnen Vorgang geschützt werden muss. Wenn mehrere Vorgänge vorhanden sind, sollten Sie verwenden die `SafeInt` Klasse anstelle von den einzelnen eigenständigen Funktionen.

Weitere Informationen zu den Vorlagentypen T "und" U, finden Sie unter [SafeInt-Funktionen](../windows/safeint-functions.md).

## <a name="requirements"></a>Anforderungen

**Header:** safeint.h

**Namespace:** Microsoft::Utilities

## <a name="see-also"></a>Siehe auch

[SafeInt-Funktionen](../windows/safeint-functions.md)<br/>
[SafeInt-Bibliothek](../windows/safeint-library.md)<br/>
[SafeInt-Klasse](../windows/safeint-class.md)