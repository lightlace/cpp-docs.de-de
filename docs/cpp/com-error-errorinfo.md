---
title: _com_error::ErrorInfo
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorInfo
helpviewer_keywords:
- ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
ms.openlocfilehash: 59ada8a7e098e57cca5641a439365851bbae2485
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155071"
---
# <a name="comerrorerrorinfo"></a>_com_error::ErrorInfo

**Microsoft-spezifisch**

Ruft das `IErrorInfo`-Objekt ab, das an den Konstruktor übergeben wurde.

## <a name="syntax"></a>Syntax

```
IErrorInfo * ErrorInfo( ) const throw( );
```

## <a name="return-value"></a>Rückgabewert

Unformatiertes `IErrorInfo`-Element, das an den Konstruktor übergeben wird.

## <a name="remarks"></a>Hinweise

Ruft das gekapselte `IErrorInfo` Element in einem `_com_error` Objekt oder NULL, wenn keine `IErrorInfo` -Element erfasst ist. Der Aufrufer muss Aufrufen `Release` für das zurückgegebene Objekt nach Verwendung.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_com_error-Klasse](../cpp/com-error-class.md)