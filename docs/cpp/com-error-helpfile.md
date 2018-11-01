---
title: _com_error::HelpFile
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpFile
helpviewer_keywords:
- HelpFile method [C++]
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
ms.openlocfilehash: 826ac53f001355127f16b7ad2a7583a0f8800de7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50433574"
---
# <a name="comerrorhelpfile"></a>_com_error::HelpFile

**Microsoft-spezifisch**

Ruft die `IErrorInfo::GetHelpFile`-Funktion auf.

## <a name="syntax"></a>Syntax

```
_bstr_t HelpFile() const;
```

## <a name="return-value"></a>Rückgabewert

Gibt das Ergebnis des `IErrorInfo::GetHelpFile` für die `IErrorInfo` -Objekt erfasst wird, innerhalb der `_com_error` Objekt. Das resultierende BSTR wird in einem `_bstr_t`-Objekt gekapselt. Wenn kein `IErrorInfo` wird aufgezeichnet, es gibt eine leere `_bstr_t`.

## <a name="remarks"></a>Hinweise

Jeder Fehler beim Aufrufen der `IErrorInfo::GetHelpFile` -Methode wird ignoriert.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_com_error-Klasse](../cpp/com-error-class.md)