---
title: Compilerfehler Fehler C2015 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2015
dev_langs: C++
helpviewer_keywords: C2015
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a04a5c113ca39dac137f2f225a8dcad9318a29bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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