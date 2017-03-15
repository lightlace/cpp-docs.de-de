---
title: Compiler-Fehler C3280 generiert | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3280
dev_langs:
- C++
helpviewer_keywords:
- C3280
ms.assetid: 86dc5bbc-8818-4786-a728-9334268d308b
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 47e008992a9f077ad8985d4a5bb6b830ec93930f
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3280"></a>Compilerfehler C3280
"Klasse": Eine Memberfunktion eines verwalteten Typs kann nicht als eine nicht verwaltete Funktion kompiliert werden  
  
 Es ist nicht möglich, Memberfunktionen mit verwalteten Klassen als nicht verwaltete Funktionen zu kompilieren.  
  
 Im folgenden Beispiel wird C3280 generiert:  
  
```  
// C3280_2.cpp  
// compile with: /clr  
ref struct A {  
   void func();  
};  
  
#pragma managed(push,off)  
  
void A::func()   // C3280  
{  
}  
  
#pragma managed(pop)  
```  

