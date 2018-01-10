---
title: Compilerwarnung (Stufe 4) C4239 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4239
dev_langs: C++
helpviewer_keywords: C4239
ms.assetid: a23dc16a-649e-4870-9a24-275de1584fcd
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 18f1c6d700de0c621ebde02c7dcb2817091677cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4239"></a>Compilerwarnung (Stufe 4) C4239
nicht dem Standard entsprechende Erweiterung: 'token': Konvertierung von 'Typ' zu 'Type'  
  
 Diese Konvertierung vom Typ wird vom C++-Standard nicht zulässig, aber es ist zulässig hier als eine Erweiterung. Diese Warnung folgt immer mindestens eine Zeile der Erläuterung ein, die Language-Regel verletzt wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4239 generiert.  
  
```  
// C4239.cpp  
// compile with: /W4 /c  
struct C {  
   C() {}  
};  
  
void func(void) {  
   C & rC = C();   // C4239  
   const C & rC2 = C();   // OK  
   rC2;  
}  
```  
  
## <a name="example"></a>Beispiel  
 Konvertierung von ganzzahligen Typs in Enum-Typ ist nicht zwingend zulässig.  
  
 Im folgenden Beispiel wird C4239 generiert.  
  
```  
// C4239b.cpp  
// compile with: /W4 /c  
enum E { value };   
struct S {   
   E e : 2;   
} s = { 5 };   // C4239   
// try the following line instead  
// } s = { (E)5 };  
```