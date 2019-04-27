---
title: _com_error::HelpContext
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpContext
helpviewer_keywords:
- HelpContext method [C++]
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
ms.openlocfilehash: a421a7fd7fa0817c74dac66946e28928b2ad82dc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155084"
---
# <a name="comerrorhelpcontext"></a>_com_error::HelpContext

**Microsoft-spezifisch**

Ruft die `IErrorInfo::GetHelpContext`-Funktion auf.

## <a name="syntax"></a>Syntax

```
DWORD HelpContext( ) const throw( );
```

## <a name="return-value"></a>Rückgabewert

Gibt das Ergebnis des `IErrorInfo::GetHelpContext` für die `IErrorInfo` -Objekt erfasst wird, innerhalb der `_com_error` Objekt. Wenn kein `IErrorInfo` -Objekt erfasst wird, wird 0 zurückgegeben.

## <a name="remarks"></a>Hinweise

Jeder Fehler beim Aufrufen der `IErrorInfo::GetHelpContext` -Methode wird ignoriert.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_com_error-Klasse](../cpp/com-error-class.md)