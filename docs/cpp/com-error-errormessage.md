---
title: _com_error::ErrorMessage | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::ErrorMessage
dev_langs:
- C++
helpviewer_keywords:
- ErrorMessage method [C++]
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9367e92110ba7fb232e89b9d950e491e5e8da5c7
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407168"
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
 Ruft der entsprechenden systemnachrichtentext für HRESULT in aufgezeichnet ab der `_com_error` Objekt. Der systemnachrichtentext wird abgerufen, indem der Aufruf der Win32 [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) Funktion. Die zurückgegebene Zeichenfolge wird von der `FormatMessage`-API zugeordnet und wird ausgegeben, wenn das `_com_error`-Objekt zerstört wird.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_error-Klasse](../cpp/com-error-class.md)