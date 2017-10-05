---
title: _bstr_t::GetAddress | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::GetAddress
dev_langs:
- C++
helpviewer_keywords:
- GetAddress method
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
caps.latest.revision: 7
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
ms.openlocfilehash: d11479a93cf19b59ae6b824f76f9b00b10fff6b2
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="bstrtgetaddress"></a>_bstr_t::GetAddress
**Microsoft-spezifisch**  
  
 Setzt etwaig vorhandene Zeichenfolgen frei und gibt die Adresse einer neu zugeordneten Zeichenfolge zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
BSTR* GetAddress( );  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den `BSTR` umschlossen von `_bstr_t`.  
  
## <a name="remarks"></a>Hinweise  
 `GetAddress` wirkt sich auf alle `_bstr_t`-Objekte aus, die ein `BSTR` freigeben. Mehr als eine `_bstr_t` kann eine `BSTR` durch die Verwendung des Kopierkonstruktors und des `operator=` freigeben.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [_bstr_t:: Assign](../cpp/bstr-t-assign.md) für eine Beispiel-mit `GetAddress`.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_bstr_t-Klasse](../cpp/bstr-t-class.md)
