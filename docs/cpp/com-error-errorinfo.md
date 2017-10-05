---
title: _com_error::errorInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::ErrorInfo
- ErrorInfo
- _com_error.ErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- ErrorInfo method
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
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
ms.openlocfilehash: e80dafb5d1472ec28631b13ab05a0dea0b4de4ba
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="comerrorerrorinfo"></a>_com_error::ErrorInfo
**Microsoft-spezifisch**  
  
 Ruft die **IErrorInfo** Objekt an den Konstruktor übergeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
IErrorInfo * ErrorInfo( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Unformatierte **IErrorInfo** Element an den Konstruktor übergeben.  
  
## <a name="remarks"></a>Hinweise  
 Ruft das gekapselte **IErrorInfo** Element in einem `_com_error` -Objekt, oder **NULL** kein **IErrorInfo** -Element erfasst ist. Der Aufrufer muss Aufrufen **Version** Verwendung für das zurückgegebene Objekt abgeschlossen.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_error-Klasse](../cpp/com-error-class.md)
