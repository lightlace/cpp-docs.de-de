---
title: Compilerfehler C2313 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2313
dev_langs:
- C++
helpviewer_keywords:
- C2313
ms.assetid: f70eb19b-c0a3-4fb2-ade1-3890a589928d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 984e9e5e9163137537c9da2cd8c14bd1271ebeb0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2313"></a>Compilerfehler C2313
'Typ1': wurde aufgefangen durch Verweis ('Typ2') in Zeile  
  
 Der Ausnahmetyp verfügt über zwei Handler. Der Verweis für den zweiten Catch ist ein Verweis auf den Typ des ersten Catch.  
  
 Im folgenden Beispiel wird C2313 generiert:  
  
```  
// C2313.cpp  
// compile with: /EHsc  
#include <eh.h>  
class C {};  
int main() {  
    try {  
        throw "ooops!";  
    }  
    catch( C& ) {}  
    catch( C ) {}   // C2313  
}  
```