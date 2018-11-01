---
title: _com_error::ErrorMessage
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorMessage
helpviewer_keywords:
- ErrorMessage method [C++]
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
ms.openlocfilehash: b1c1b5a79cdf5ee2a4a17d969d23ce0d0d85ab54
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50504493"
---
# <a name="comerrorerrormessage"></a>_com_error::ErrorMessage

**Microsoft-spezifisch**

Ruft die Zeichenfolgenmeldung für das im `_com_error`-Objekt gespeicherte HRESULT ab.

## <a name="syntax"></a>Syntax

```
const TCHAR * ErrorMessage( ) const throw( );
```

## <a name="return-value"></a>Rückgabewert

Gibt die zeichenfolgenmeldung zurück, für der HRESULT-Wert in aufgezeichnet der `_com_error` Objekt. Wenn HRESULT ein zugeordneter 16-Bit ist [wCode](../cpp/com-error-wcode.md), klicken Sie dann eine generische Meldung "`IDispatch error #<wCode>`" wird zurückgegeben. Wenn keine Nachricht gefunden wird, wird eine generische Meldung "`Unknown error #<hresult>`" zurückgegeben. Die zurückgegebene Zeichenfolge ist entweder eine Unicode- oder eine multibyte-Zeichenfolge, abhängig vom Zustand der _UNICODE-Makro.

## <a name="remarks"></a>Hinweise

Ruft der entsprechenden systemnachrichtentext für HRESULT in aufgezeichnet ab der `_com_error` Objekt. Der systemnachrichtentext wird abgerufen, indem der Aufruf der Win32 [FormatMessage](/windows/desktop/api/winbase/nf-winbase-formatmessage) Funktion. Die zurückgegebene Zeichenfolge wird von der `FormatMessage`-API zugeordnet und wird ausgegeben, wenn das `_com_error`-Objekt zerstört wird.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_com_error-Klasse](../cpp/com-error-class.md)