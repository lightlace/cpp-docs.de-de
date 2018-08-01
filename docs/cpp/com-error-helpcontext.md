---
title: _com_error::HelpContext | Microsoft-Dokumentation
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
ms.openlocfilehash: b1edf990697aa6becca0ad377f18e8f7045c96a4
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401843"
---
# <a name="comerrorhelpcontext"></a>_com_error::HelpContext
**Microsoft-spezifisch**  
  
 Ruft die `IErrorInfo::GetHelpContext`-Funktion auf.  
  
## <a name="syntax"></a>Syntax  
  
```  
DWORD HelpContext( ) const throw( );  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt das Ergebnis des `IErrorInfo::GetHelpContext` für die `IErrorInfo` -Objekt erfasst wird, innerhalb der `_com_error` Objekt. Wenn kein `IErrorInfo` -Objekt erfasst wird, wird 0 zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Jeder Fehler beim Aufrufen der `IErrorInfo::GetHelpContext` -Methode wird ignoriert.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_error-Klasse](../cpp/com-error-class.md)