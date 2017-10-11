---
title: Compiler-Fehler C3133 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3133
dev_langs:
- C++
helpviewer_keywords:
- C3133
ms.assetid: 4a709405-b67b-4061-8a2a-19fa5fb34a2a
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9373f8990bf02c3c0436a14d4a9d22fc8a7338bf
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3133"></a>Compiler-Fehler C3133 generiert
Attribute können nicht auf C++-Variablenargumente angewendet werden  
  
 Ein Attribut wurde falsch angewendet. Attribute können nicht auf die Auslassungspunkte, die Variable Argumente darstellt angewendet werden.  
  
 Weitere Informationen finden Sie unter [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3133 generiert.  
  
```  
// C3133.cpp  
// compile with: /clr /c  
ref struct MyAttr: System::Attribute {};   
void Func([MyAttr]...);   // C3133  
void Func2([MyAttr] int i);   // OK  
```
