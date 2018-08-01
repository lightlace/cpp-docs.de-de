---
title: _com_error::Description | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::Description
dev_langs:
- C++
helpviewer_keywords:
- Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 848709fa6cbbbfb4166750f86540de2433a73023
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404027"
---
# <a name="comerrordescription"></a>_com_error::Description
**Microsoft-spezifisch**  
  
 Ruft die `IErrorInfo::GetDescription`-Funktion auf.  
  
## <a name="syntax"></a>Syntax  
  
```  
_bstr_t Description( ) const;  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt das Ergebnis des `IErrorInfo::GetDescription` für die `IErrorInfo` -Objekt erfasst wird, innerhalb der `_com_error` Objekt. Das resultierende `BSTR` wird in einem `_bstr_t`-Objekt gekapselt. Wenn kein `IErrorInfo` wird aufgezeichnet, es gibt eine leere `_bstr_t`.  
  
## <a name="remarks"></a>Hinweise  
 Ruft die `IErrorInfo::GetDescription` -Funktion und ruft `IErrorInfo` aufgezeichnet, die innerhalb der `_com_error` Objekt. Jeder Fehler beim Aufrufen der `IErrorInfo::GetDescription` -Methode wird ignoriert.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_error-Klasse](../cpp/com-error-class.md)