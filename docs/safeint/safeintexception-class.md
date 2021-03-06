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
ms.openlocfilehash: 2998bbb83fd568d7ff627d6598c32fb5b17c1e40
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "65515565"
---
# <a name="safeintexception-class"></a>SafeIntException-Klasse

Die `SafeInt`-Klasse verwendet `SafeIntException`, um festzustellen, warum ein mathematischer Vorgang nicht abgeschlossen werden kann.

> [!NOTE]
> Die neueste Version dieser Bibliothek befindet sich unter [https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt).

## <a name="syntax"></a>Syntax

```cpp
class SafeIntException;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

name                                                    | Beschreibung
------------------------------------------------------- | ------------------------------------
[SafeIntException::SafeIntException](#safeintexception) | Erstellt ein `SafeIntException`-Objekt.

## <a name="remarks"></a>Anmerkungen

Die [SafeInt-Klasse](../safeint/safeint-class.md) ist die einzige Klasse, die die `SafeIntException`-Klasse verwendet.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`SafeIntException`

## <a name="requirements"></a>Anforderungen

**Header:** „safeint.h“

**Namespace:** msl::utilities

## <a name="safeintexception"></a>SafeIntException::SafeIntException

Erstellt ein `SafeIntException`-Objekt.

```cpp
SafeIntException();

SafeIntException(
   SafeIntError code
);
```

### <a name="parameters"></a>Parameter

*Code*<br/>
[in] Ein Aufzählungsdatenwert, der den aufgetretenen Fehler beschreibt.

### <a name="remarks"></a>Anmerkungen

Die möglichen Werte für *code* werden in der Datei „Safeint.h“ definiert. Der Einfachheit halber sind die möglichen Werte auch hier aufgeführt.

- `SafeIntNoError`
- `SafeIntArithmeticOverflow`
- `SafeIntDivideByZero`
