---
title: nothrow_t-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- nothrow_t
dev_langs:
- C++
helpviewer_keywords:
- nothrow_t class
ms.assetid: dc7d5d42-ed5a-4919-88fe-bbad519b7a1d
caps.latest.revision: 20
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
translationtype: Machine Translation
ms.sourcegitcommit: 85c900f2263ae1c1089478badc85388e3b5e8548
ms.openlocfilehash: b490cccf048b5d5b9be53508331cba89e66c952f
ms.lasthandoff: 02/24/2017

---
# <a name="nothrowt-structure"></a>nothrow_t-Struktur
Die Struktur wird als Funktionsparameter für „operator new“ verwendet, um anzugeben, dass die Funktion zum Melden eines Zuordnungsfehlers keine Ausnahme auslösen, sondern einen NULL-Zeiger zurückgeben soll.  
  
## <a name="syntax"></a>Syntax  
  
```
struct std::nothrow_t {};
```  
  
## <a name="remarks"></a>Hinweise  
 Die Struktur hilft dem Compiler beim Auswählen der richtigen Version des Konstruktors. [nothrow](../standard-library/new-functions.md#nothrow) ist ein Synonym für Objekte des Typs `std::nothrow_t`.  
  
## <a name="example"></a>Beispiel  
 Beispiele zur Verwendung von `std::nothrow_t` als Funktionsparameter finden Sie unter [operator new](../standard-library/new-operators.md#operator_new) und [operator new&#91;&#93;](../standard-library/new-operators.md#operator_new_arr).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<new>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)




