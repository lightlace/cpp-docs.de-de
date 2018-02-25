---
title: nothrow_t-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- nothrow_t
dev_langs:
- C++
helpviewer_keywords:
- nothrow_t class
ms.assetid: dc7d5d42-ed5a-4919-88fe-bbad519b7a1d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4854fb4e763679a63b14147cec8f1f37310475fe
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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
 Beispiele zur Verwendung von `std::nothrow_t` als Funktionsparameter finden Sie unter [operator new](../standard-library/new-operators.md#op_new) und [operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<new>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)



