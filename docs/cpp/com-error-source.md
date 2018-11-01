---
title: _com_error::Source
ms.date: 11/04/2016
f1_keywords:
- _com_error::Source
helpviewer_keywords:
- Source method [C++]
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
ms.openlocfilehash: 682070877f269967405677d027b20707c8366f61
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644430"
---
# <a name="comerrorsource"></a>_com_error::Source

**Microsoft-spezifisch**

Ruft die `IErrorInfo::GetSource`-Funktion auf.

## <a name="syntax"></a>Syntax

```
_bstr_t Source() const;
```

## <a name="return-value"></a>Rückgabewert

Gibt das Ergebnis des `IErrorInfo::GetSource` für die `IErrorInfo` -Objekt erfasst wird, innerhalb der `_com_error` Objekt. Das resultierende `BSTR` wird in einem `_bstr_t`-Objekt gekapselt. Wenn kein `IErrorInfo` wird aufgezeichnet, es gibt eine leere `_bstr_t`.

## <a name="remarks"></a>Hinweise

Jeder Fehler beim Aufrufen der `IErrorInfo::GetSource` -Methode wird ignoriert.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_com_error-Klasse](../cpp/com-error-class.md)