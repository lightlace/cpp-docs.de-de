---
title: SafeIntException-Klasse
ms.date: 10/22/2018
ms.topic: reference
f1_keywords:
- SafeIntException Class
- SafeIntException
- SafeIntException.SafeIntException
- SafeIntException::SafeIntException
helpviewer_keywords:
- SafeIntException class
- SafeIntException, constructor
ms.assetid: 88bef958-1f48-4d55-ad4f-d1f9581a293a
ms.openlocfilehash: 80a1573c2f43b1f4b31731083974f87ba389fac2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566659"
---
# <a name="safeintexception-class"></a>SafeIntException-Klasse

Die `SafeInt` -Klasse `SafeIntException` , warum ein mathematischer Vorgang nicht abgeschlossen werden kann.

> [!NOTE]
> Die neueste Version dieser Bibliothek befindet sich unter [ https://github.com/dcleblanc/SafeInt ](https://github.com/dcleblanc/SafeInt).

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
