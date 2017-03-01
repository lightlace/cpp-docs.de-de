---
title: Compiler-Fehler C3181 generiert | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3181
dev_langs:
- C++
helpviewer_keywords:
- C3181
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
caps.latest.revision: 10
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 4229a9d9811bad46035451c5d64b7ed06da476d2
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3181"></a>Compiler-Fehler C3181 generiert
'Typ': Ungültiger Operand für Operator  
  
Ein ungültiger Parameter übergeben wurde, um die [Typeid](../../windows/typeid-cpp-component-extensions.md) Operator. Der Parameter muss ein verwalteter Typ sein.  
  
Beachten Sie, dass der Compiler Aliasnamen für systemeigene Typen verwendet, die Typen in der common Language Runtime zugeordnet.  
  
Im folgende Beispiel wird C3181 generiert:  
  
```  
// C3181a.cpp  
// compile with: /clr  
using namespace System;  
  
int main() {  
   Type ^pType1 = interior_ptr<int>::typeid;   // C3181  
   Type ^pType2 = int::typeid;   // OK  
}  
```  

