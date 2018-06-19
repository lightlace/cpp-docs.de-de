---
title: _com_error::ErrorMessage | Microsoft Docs
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
ms.openlocfilehash: c16b8bb6859cd65b534d804764257b901050995b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411232"
---
# <a name="comerrorerrormessage"></a>_com_error::ErrorMessage
**Microsoft-spezifisch**  
  
 Ruft die Zeichenfolgenmeldung für das `HRESULT`-Objekt ab, das im `_com_error`-Objekt gespeichert ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
const TCHAR * ErrorMessage( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt die Zeichenfolgenmeldung für das `HRESULT`-Objekt zurück, das innerhalb des `_com_error`-Objekts aufgezeichnet wird. Wenn die `HRESULT` ist ein zugeordneter 16-Bit [wCode](../cpp/com-error-wcode.md), wird eine generische Meldung "`IDispatch error #<wCode>`" wird zurückgegeben. Wenn keine Nachricht gefunden wird, wird eine generische Meldung "`Unknown error #<hresult>`" zurückgegeben. Die zurückgegebene Zeichenfolge ist entweder eine Unicode- oder multibyte-Zeichenfolge, abhängig vom Status des der **_UNICODE** Makro.  
  
## <a name="remarks"></a>Hinweise  
 Ruft den entsprechenden Systemnachrichtentext für das `HRESULT`-Objekt ab, das innerhalb des `_com_error`-Objekts erfasst ist. Der systemnachrichtentext wird durch Aufruf der Win32 abgerufen [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) Funktion. Die zurückgegebene Zeichenfolge wird von der `FormatMessage`-API zugeordnet und wird ausgegeben, wenn das `_com_error`-Objekt zerstört wird.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_error-Klasse](../cpp/com-error-class.md)