---
title: _com_error::GUID | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::GUID
dev_langs:
- C++
helpviewer_keywords:
- GUID method [C++]
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 6a1d0349344362853215a2c47db166bc4b885187
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="comerrorguid"></a>_com_error::GUID
**Microsoft-spezifisch**  
  
 Aufrufe **IErrorInfo:: GetGuid** Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
GUID GUID( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt das Ergebnis der **IErrorInfo:: GetGuid** für die **IErrorInfo** -Objekt erfasst wird, innerhalb der `_com_error` Objekt. Wenn kein **IErrorInfo** -Objekt erfasst wird, gibt es `GUID_NULL`.  
  
## <a name="remarks"></a>Hinweise  
 Jeder Fehler beim Aufrufen der **IErrorInfo:: GetGuid** -Methode wird ignoriert.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_error-Klasse](../cpp/com-error-class.md)
