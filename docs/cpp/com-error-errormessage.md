---
title: _com_error::ErrorMessage
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorMessage
helpviewer_keywords:
- ErrorMessage method [C++]
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
ms.openlocfilehash: 44fc9755cd69050ea82145636f01614258943794
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500580"
---
# <a name="_com_errorerrormessage"></a>_com_error::ErrorMessage

**Microsoft-spezifisch**

Ruft die Zeichenfolgenmeldung für das im `_com_error`-Objekt gespeicherte HRESULT ab.

## <a name="syntax"></a>Syntax

```
const TCHAR * ErrorMessage( ) const throw( );
```

## <a name="return-value"></a>Rückgabewert

Gibt die Zeichen folgen Meldung für das HRESULT zurück, `_com_error` das innerhalb des-Objekts aufgezeichnet wird. Wenn HRESULT ein zugeordneter 16-Bit- [wCode](../cpp/com-error-wcode.md)ist, wird eine generische`IDispatch error #<wCode>`Meldung "" zurückgegeben. Wenn keine Nachricht gefunden wird, wird eine generische Meldung "`Unknown error #<hresult>`" zurückgegeben. Die zurückgegebene Zeichenfolge ist entweder eine Unicode-oder eine Multibytezeichenfolge, abhängig vom Zustand des _UNICODE-Makros.

## <a name="remarks"></a>Hinweise

Ruft den passenden Systemmeldungs Text für HRESULT ab, der `_com_error` innerhalb des-Objekts aufgezeichnet wird. Der Text der Systemmeldung wird durch Aufrufen der Win32 [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage) -Funktion abgerufen. Die zurückgegebene Zeichenfolge wird von der `FormatMessage`-API zugeordnet und wird ausgegeben, wenn das `_com_error`-Objekt zerstört wird.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_com_error-Klasse](../cpp/com-error-class.md)