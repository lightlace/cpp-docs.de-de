---
title: _com_error::Description | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::Description
dev_langs: C++
helpviewer_keywords: Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f3ed306a8eba4e76c2eefc738b617117188e85c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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