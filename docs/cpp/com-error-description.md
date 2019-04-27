---
title: _com_error::Description
ms.date: 11/04/2016
f1_keywords:
- _com_error::Description
helpviewer_keywords:
- Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
ms.openlocfilehash: a517c40e9adfbda2d790ce41a48ccf8658bcd3e0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155110"
---
# <a name="comerrordescription"></a>_com_error::Description

**Microsoft-spezifisch**

Ruft die `IErrorInfo::GetDescription`-Funktion auf.

## <a name="syntax"></a>Syntax

```
_bstr_t Description( ) const;
```

## <a name="return-value"></a>Rückgabewert

Gibt das Ergebnis des `IErrorInfo::GetDescription` für die `IErrorInfo` -Objekt erfasst wird, innerhalb der `_com_error` Objekt. Das resultierende `BSTR` wird in einem `_bstr_t`-Objekt gekapselt. Wenn kein `IErrorInfo` wird aufgezeichnet, es gibt eine leere `_bstr_t`.

## <a name="remarks"></a>Hinweise

Ruft die `IErrorInfo::GetDescription` -Funktion und ruft `IErrorInfo` aufgezeichnet, die innerhalb der `_com_error` Objekt. Jeder Fehler beim Aufrufen der `IErrorInfo::GetDescription` -Methode wird ignoriert.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_com_error-Klasse](../cpp/com-error-class.md)