---
title: _com_error::Description | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error.Description
- _com_error::Description
dev_langs:
- C++
helpviewer_keywords:
- Description method
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 0d91f6fded1fa1c4ea4d44cadd0d9285913b5f42
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="comerrordescription"></a>_com_error::Description
**Microsoft-spezifisch**  
  
 Aufrufe **IErrorInfo:: GetDescription** Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
_bstr_t Description( ) const;  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt das Ergebnis der **IErrorInfo:: GetDescription** für die **IErrorInfo** -Objekt erfasst wird, innerhalb der `_com_error` Objekt. Das resultierende `BSTR` wird in einem `_bstr_t`-Objekt gekapselt. Wenn kein **IErrorInfo** wird aufgezeichnet, es gibt ein leeres `_bstr_t`.  
  
## <a name="remarks"></a>Hinweise  
 Ruft die **IErrorInfo:: GetDescription** -Funktion und ruft **IErrorInfo** aufgezeichnet, die innerhalb der `_com_error` Objekt. Jeder Fehler beim Aufrufen der **IErrorInfo:: GetDescription** -Methode wird ignoriert.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_error-Klasse](../cpp/com-error-class.md)
