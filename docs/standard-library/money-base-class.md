---
title: money_base-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- locale/std::money_base
- money_base
dev_langs:
- C++
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
caps.latest.revision: 19
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 4af0f51a820fc0011285b6c5a690f496e8fd4afe
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="moneybase-class"></a>money_base-Klasse
Die Klasse beschreibt eine Enumeration und eine Struktur, die für alle Spezialisierungen der Vorlagenklasse [moneypunct](../standard-library/moneypunct-class.md) gebräuchlich ist.  
  
## <a name="syntax"></a>Syntax  
```    
struct pattern
{
   char field[_PATTERN_FIELD_SIZE];
};  
```  
## <a name="remarks"></a>Hinweise  
 Die Enumeration **part** beschreibt die möglichen Werte in Elementen des Array-Felds im Strukturmuster. Als Werte von **part** dienen:  
  
- **none**, um auf null oder mehr Leerzeichen abzustimmen bzw. nichts zu generieren.  
  
- **sign**, um auf ein positives bzw. negatives Vorzeichen abzustimmen oder um ein positives bzw. negatives Vorzeichen zu generieren.  
  
- **space**, um auf null oder mehr Leerzeichen abzustimmen bzw. um ein Leerzeichen zu generieren.  
  
- **symbol**, um auf ein Währungssymbol abzustimmen bzw. um ein Währungssymbol zu generieren.  
  
- **value**, um auf einen monetären Wert abzustimmen bzw. um einen monetären Wert zu generieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<locale>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)




