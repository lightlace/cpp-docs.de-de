---
title: Compilerwarnung (Stufe 3) C4265 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4265
dev_langs:
- C++
helpviewer_keywords:
- C4265
ms.assetid: 20547159-6f30-4cc4-83aa-927884c8bb4c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a0c859e69095b1a7e6b756b0bcc7ca8e74ba8826
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4265"></a>Compilerwarnung (Stufe 3) C4265
'Klasse': Klasse verfügt über virtuelle Funktionen, aber der Destruktor ist nicht virtuell  
  
 Wenn eine Klasse virtuelle Funktionen, aber nicht virtuellen Destruktor aufweist, möglicherweise Objekte des Typs nicht ordnungsgemäß zerstört werden, wenn die Klasse über einen Zeiger Basisklasse zerstört wird.  
  
 Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .  
  
 Im folgenden Beispiel wird C4265 generiert:  
  
```  
// C4265.cpp  
// compile with: /W3 /c  
#pragma warning(default : 4265)  
class B  
{  
public:  
   virtual void vmf();  
  
   ~B();  
   // try the following line instead  
   // virtual ~B();  
};   // C4265  
  
int main()  
{  
   B b;  
}  
```