---
title: Compilerfehler C3652 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3652
dev_langs: C++
helpviewer_keywords: C3652
ms.assetid: 15d68737-177e-41f1-80e0-7c3e2afdf0fc
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4bade460d97b8d7dcb38e7d37fa87f2910047c47
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3652"></a>Compilerfehler C3652
"override": eine Funktion, die explizit überschreibt muss virtuell sein  
  
 Eine Funktion, die ein explizites Überschreiben muss virtuell sein. Weitere Informationen finden Sie unter [explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md).  
  
 Im folgende Beispiel wird C3652 generiert:  
  
```  
// C3652.cpp  
// compile with: /clr /c  
public interface class I {  
   void f();  
};  
  
public ref struct R : I {  
   void f() = I::f {}   // C3652  
   // try the following line instead  
   // virtual void f() = I::f {}  
};  
```