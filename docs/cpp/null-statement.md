---
title: NULL-Anweisung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- expressions [C++], null
- null statement
- null values, expressions
ms.assetid: 606f5953-55f0-40c8-ae03-3ee3a819b851
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: f15fda458fe604d0501c4daa87e6a76cd0422260
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="null-statement"></a>NULL-Anweisung
Die "null-Anweisung" ist eine Ausdrucksanweisung, bei der *Ausdruck* fehlt. Dies ist nützlich, wenn in der Syntax der Sprache eine Anweisung erwartet wird, jedoch keine Ausdrucksauswertung. Die Anweisung besteht aus einem Semikolon.  
  
 NULL-Anweisungen werden normalerweise als Platzhalter in Iterationsanweisungen oder als Anweisungen verwendet, um Bezeichnungen am Ende von Verbundanweisungen oder Funktionen zu platzieren.  
  
 Das folgende Codefragment zeigt, wie Sie eine Zeichenfolge zu einer anderen kopieren und die NULL-Anweisung integrieren:  
  
```  
// null_statement.cpp  
char *myStrCpy( char *Dest, const char *Source )  
{  
    char *DestStart = Dest;  
  
    // Assign value pointed to by Source to  
    // Dest until the end-of-string 0 is  
    // encountered.  
    while( *Dest++ = *Source++ )  
        ;   // Null statement.  
  
    return DestStart;  
}  
  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrucksanweisung](../cpp/expression-statement.md)
