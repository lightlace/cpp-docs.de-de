---
title: Compilerwarnung (Stufe 4) C4816 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4816
dev_langs: C++
helpviewer_keywords: C4816
ms.assetid: 60f730ae-d942-4db9-ab97-41d4a874d8da
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8002b165d80763c00fe7fa7d2b3c44cddbd2e199
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4816"></a>Compilerwarnung (Stufe 4) C4816
'Param': Parameter hat ein Array der Größe 0, das abgeschnitten wird (sofern das Objekt nicht als Verweis übergeben wird).  
  
 Ein Parameter für ein Objekt mit einem Array der Größe 0 wurde nicht als Verweis übergeben. Das Array wird bei der Übergabe des Objekts nicht kopiert.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4816 generiert.  
  
```  
// C4816.cpp  
// compile with: /W4  
#include <stdio.h>  
  
extern "C" int printf_s(const char *, ...);  
  
#pragma warning(disable : 4200)  
  
struct S1  
{  
    int i;  
    char cArr[];  
};  
  
void TestErr(S1 s1)   // C4816 param with zero-array   
                      // not passed by reference  
{  
    printf_s("%d %c %c\n", s1.i, s1.cArr[0], s1.cArr[1]);  
}  
  
void TestOk(S1 &s1)  
{  
    printf_s("%d %c %c\n", s1.i, s1.cArr[0], s1.cArr[1]);  
}  
  
int main()  
{  
    S1 myS_1 = { 6, 'a', 'b', 'c' };  
    TestErr(myS_1);  
    TestOk(myS_1);  
}  
```