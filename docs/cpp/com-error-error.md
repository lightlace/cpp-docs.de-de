---
title: _com_error::Error | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error.Error
- _com_error::Error
- Error
dev_langs:
- C++
helpviewer_keywords:
- Error method
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
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
ms.openlocfilehash: df8f409430b802350c1696592fc7f096283d015d
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="comerrorerror"></a>_com_error::Error
**Microsoft-spezifisch**  
  
 Ruft das an den Konstruktor übergebene `HRESULT` ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
HRESULT Error( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Unformatiertes `HRESULT`-Element, das an den Konstruktor übergeben wird.  
  
## <a name="remarks"></a>Hinweise  
 Ruft das gekapselte `HRESULT`-Element in einem `_com_error`-Objekt ab.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_error-Klasse](../cpp/com-error-class.md)
