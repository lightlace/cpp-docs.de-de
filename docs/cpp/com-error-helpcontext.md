---
title: _com_error::HelpContext | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::HelpContext
dev_langs:
- C++
helpviewer_keywords:
- HelpContext method [C++]
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7123fcf5859ce3fc373b29b4cb3e7b32109b464e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32410823"
---
# <a name="comerrorhelpcontext"></a>_com_error::HelpContext
**Microsoft-spezifisch**  
  
 Aufrufe **IErrorInfo:: GetHelpContext** Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
DWORD HelpContext( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt das Ergebnis der **IErrorInfo:: GetHelpContext** für die **IErrorInfo** -Objekt erfasst wird, innerhalb der `_com_error` Objekt. Wenn kein **IErrorInfo** -Objekt erfasst wird, wird 0 zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Jeder Fehler beim Aufrufen der **IErrorInfo:: GetHelpContext** -Methode wird ignoriert.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_error-Klasse](../cpp/com-error-class.md)