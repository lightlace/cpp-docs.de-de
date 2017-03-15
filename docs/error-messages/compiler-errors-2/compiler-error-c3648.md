---
title: Compiler-Fehler C3648 generiert | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3648
dev_langs:
- C++
helpviewer_keywords:
- C3648
ms.assetid: 5d042989-41cb-4cd0-aa50-976b70146aaf
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
ms.openlocfilehash: bbc097048600700592d2ebb30d939ba216434d84
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3648"></a>Compilerfehler C3648
Für diese explizite Überschreibungssyntax ist /clr:oldSyntax erforderlich.  
  
Bei der Kompilierung für die neueste verwaltete Syntax Überschreiben der Compiler gefunden explizite Syntax für frühere Versionen, die nicht mehr unterstützt wird.  
  
Weitere Informationen finden Sie unter [Explizite Overrides](../../windows/explicit-overrides-cpp-component-extensions.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3648 generiert:  
  
```  
// C3648.cpp  
// compile with: /clr  
public interface struct I {  
   void f();  
};  
  
public ref struct R : I {  
   virtual void I::f() {}   // C3648  
   // try the following line instead  
   // virtual void f() = I::f{}  
};  
```
