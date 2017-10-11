---
title: Compilerfehler C3461 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3461
dev_langs:
- C++
helpviewer_keywords:
- C3461
ms.assetid: bd66833a-545d-445a-bdfe-dee771a450a4
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 27cc201ff7b11b5a44179d5a678bee42d0b21609
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3461"></a>Compilerfehler C3461
'Typ': Nur ein verwalteter Typ kann weitergeleitet werden.  
  
 Die Typweiterleitung ist nur bei CLR-Typen möglich.  Finden Sie unter [Klassen und Strukturen](../../windows/classes-and-structs-cpp-component-extensions.md) für Weitere Informationen.  
  
 Weitere Informationen finden Sie unter [Typweiterleitung (C + c++ / CLI)](../../windows/type-forwarding-cpp-cli.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Komponente erstellt:  
  
```  
// C3461.cpp  
// compile with: /clr /LD  
public ref class R {};  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3461 generiert:  
  
```  
// C3461b.cpp  
// compile with: /clr /c  
#using "C3461.dll"  
class N {};  
[assembly:TypeForwardedTo(N::typeid)];   // C3461  
[assembly:TypeForwardedTo(R::typeid)];   // OK  
```
