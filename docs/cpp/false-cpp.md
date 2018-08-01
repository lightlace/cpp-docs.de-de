---
title: "\"false\" (C++) | Microsoft-Dokumentation"
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- false_cpp
dev_langs:
- C++
helpviewer_keywords:
- false keyword [C++]
ms.assetid: cc13aec5-1f02-4d38-8dbf-5473ea2b354f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b45db3a1226a9069c03ff928227a8719c83eb65
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406519"
---
# <a name="false-c"></a>false (C++)
Das Schlüsselwort ist eines der beiden Werte für eine Variable vom Typ ["bool"](../cpp/bool-cpp.md) oder ein bedingter Ausdruck (ein bedingter Ausdruck ist jetzt ein **"true"** booleschen Ausdruck). Z. B. wenn `i` ist eine Variable vom Typ **"bool"**, `i = false;` Anweisung weist **"false"** zu `i`.  
  
## <a name="example"></a>Beispiel  
  
```cpp 
// bool_false.cpp  
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