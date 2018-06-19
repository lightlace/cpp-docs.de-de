---
title: Compilerfehler Fehler C2015 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2015
dev_langs:
- C++
helpviewer_keywords:
- C2015
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 91c682aadeab5a572ec2bb5c2e649a1511af77ef
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33165622"
---
# <a name="compiler-error-c2015"></a>Compilerfehler Fehler C2015
zu viele Zeichen in der Konstante  
  
 Eine Zeichenkonstante enthält mehr als zwei Zeichen. Der Grenzwert ist ein Zeichen für standard Zeichenkonstanten und zwei Zeichen für lange Zeichenkonstanten.  
  
 Eine Escapesequenz, z. B. \t, wird in ein einzelnes Zeichen konvertiert.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2015 generiert:  
  
```  
// C2015.cpp  
// compile with: /c  
  
char test1 = 'error';   // C2015  
char test2 = 'e';   // OK  
```  
  
## <a name="example"></a>Beispiel  
 C2015 kann auch auftreten, wenn eine Microsoft-Erweiterung Zeichenkonstanten in ganze Zahlen konvertiert.  Im folgenden Beispiel wird C2015 generiert:  
  
```  
// C2015b.cpp  
#include <stdio.h>  
  
int main()   
{  
    int a = 'abcde';   // C2015  
  
    int b = 'a';   // 'a' = ascii 0x61  
    printf_s("%x\n", b);  
}  
```