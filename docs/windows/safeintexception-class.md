---
title: SafeIntException-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/27/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeIntException Class
- SafeIntException
- SafeIntException.SafeIntException
- SafeIntException::SafeIntException
dev_langs:
- C++
helpviewer_keywords:
- SafeIntException class
- SafeIntException, constructor
ms.assetid: 88bef958-1f48-4d55-ad4f-d1f9581a293a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4ffd82f80b8af0b53ca86ca3daded84580e1e07b
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235736"
---
# <a name="safeintexception-class"></a>SafeIntException-Klasse

Die `SafeInt` -Klasse `SafeIntException` , warum ein mathematischer Vorgang nicht abgeschlossen werden kann.

## <a name="syntax"></a>Syntax

```cpp
class SafeIntException;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                                                    | Beschreibung
------------------------------------------------------- | ------------------------------------
[SafeIntException::SafeIntException](#safeintexception) | Erstellt ein `SafeIntException`-Objekt.

## <a name="remarks"></a>Hinweise

Die [SafeInt-Klasse](../windows/safeint-class.md) ist die einzige Klasse, die verwendet die `SafeIntException` Klasse.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`SafeIntException`

## <a name="requirements"></a>Anforderungen

**Header:** safeint.h

**Namespace:** MSL:: Utilities

## <a name="safeintexception"></a>SafeIntException:: SafeIntException

Erstellt ein `SafeIntException`-Objekt.

```cpp
SafeIntException();

SafeIntException(
   SafeIntError code
);
```

### <a name="parameters"></a>Parameter

*Code*<br/>
[in] Ein Aufzählungsdaten-Wert, der den Fehler beschreibt, der aufgetreten sind.

### <a name="remarks"></a>Hinweise

Die möglichen Werte für *Code* werden in der Datei Safeint.h definiert. Der Einfachheit halber sind die möglichen Werte auch hier aufgeführt.

- `SafeIntNoError`
- `SafeIntArithmeticOverflow`
- `SafeIntDivideByZero`
