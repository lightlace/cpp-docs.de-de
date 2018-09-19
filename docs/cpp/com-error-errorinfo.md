---
title: _com_error::errorInfo | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::ErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1fc2906827e6a465106a3dbdcb8b63c7b53a39ee
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039347"
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