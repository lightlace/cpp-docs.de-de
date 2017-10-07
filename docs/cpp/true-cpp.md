---
title: "\"true\" (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- true_cpp
dev_langs:
- C++
helpviewer_keywords:
- true keyword [C++]
ms.assetid: 96be2a70-51c3-4250-9752-874d25a5a11e
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: b10cf33ff93a01347ee8c8e7fc56bb5be8058f3a
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="true-c"></a>true (C++)
## <a name="syntax"></a>Syntax  
  
```  
  
      bool-identifier = true ;  
bool-expression logical-operator true ;  
```  
  
## <a name="remarks"></a>Hinweise  
 Dieses Schlüsselwort ist einer der beiden Werte für eine Variable vom Typ [Bool](../cpp/bool-cpp.md) oder ein bedingter Ausdruck (ein bedingter Ausdruck ist jetzt boolescher Ausdruck "true"). Wenn `i` ist vom Typ `bool`, klicken Sie dann die Anweisung `i = true;` weist **"true"** auf `i`.  
  
## <a name="example"></a>Beispiel  
  
```  
// bool_true.cpp  
#include <stdio.h>  
int main()  
{  
    bool bb = true;  
    printf_s("%d\n", bb);  
    bb = false;  
    printf_s("%d\n", bb);  
}  
```  
  
```Output  
1  
0  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselwörter](../cpp/keywords-cpp.md)
