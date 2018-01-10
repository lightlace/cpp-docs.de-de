---
title: Compilerwarnung (Stufe 3) C4534 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: c4534
dev_langs: C++
helpviewer_keywords: C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6d9ea2cc6fb15edf61610e96a728e985b78be468
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4534"></a>Compilerwarnung (Stufe 3) C4534
'Konstruktor' werden nicht auf einen Standardkonstruktor für die Klasse 'Klasse' aufgrund der Standardargument  
  
 Eine nicht verwaltete Klasse kann einen Konstruktor mit Parametern, die Standardwerte besitzen und der Compiler wird dies als den Standardkonstruktor verwenden. Eine Klasse gekennzeichnet wird, mit dem `value` Schlüsselwort wird nicht verwenden Sie einen Konstruktor mit standardmäßigen Werten für die Parameter als einen Standardkonstruktor.  
  
 Weitere Informationen finden Sie unter [Klassen und Strukturen](../../windows/classes-and-structs-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird C4534 generiert:  
  
```  
// C4534.cpp  
// compile with: /W3 /clr /WX  
value class MyClass {  
public:  
   int ii;  
   MyClass(int i = 9) {   // C4534, will not be the default constructor  
      i++;  
   }  
};  
  
int main() {  
   MyClass ^ xx = gcnew MyClass;  
   xx->ii = 0;  
}  
```