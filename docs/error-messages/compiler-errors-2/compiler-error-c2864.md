---
title: Compilerfehler C2864 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2864
dev_langs: C++
helpviewer_keywords: C2864
ms.assetid: d0ca2ad9-90a6-4aef-8511-98a3b414c102
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b463e8036b8bf452729ddfe11dea73aa9aae3a3e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2864"></a>Compilerfehler C2864
'Variable': Ein statisches Datenmember mit einem Initialisierer in der Klasse muss einen nicht flüchtigen konstant integralen Typ haben  
  
 Verwenden Sie eine Memberdefinitionsanweisung, um einen Datenmember vom Typ `static` zu initialisieren, der als `volatile`, nicht-`const` oder ganzzahlig definiert wird. Solche Datenmember können nicht in einer Deklaration initialisiert werden.  
  
 In diesem Beispiel wird C2864 generiert:  
  
```  
// C2864.cpp  
// compile with: /c  
class B  {  
private:  
   int a = 3;   // OK   
   static int b = 3;   // C2864  
   volatile static int c = 3;   // C2864  
   volatile static const int d = 3;   // C2864  
   const static long long e = 3;   // OK  
   static const double f = 3.33;   // C2864  
};  
```  
  
 Im folgenden Beispiel wird die Behebung von C2864 gezeigt:  
  
```  
// C2864b.cpp  
// compile with: /c  
class C  {  
private:  
   int a = 3;  
   static int b; // = 3; C2864  
   volatile static int c; // = 3; C2864  
   volatile static const int d; // = 3; C2864  
   static const long long e = 3;  
   static const double f; // = 3.33; C2864  
};  
  
// Initialize static volatile, non-const, or non-integral  
// data members when defined, not when declared:  
int C::b = 3;  
volatile int C::c = 3;  
volatile const int C::d = 3;  
const double C::f = 3.33;  
```