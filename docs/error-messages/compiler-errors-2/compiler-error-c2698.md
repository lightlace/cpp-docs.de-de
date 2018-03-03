---
title: Compiler-Fehler C2698 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2698
dev_langs:
- C++
helpviewer_keywords:
- C2698
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b2bc9be3cfa38b4789feb35ae57015b78ad079c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2698"></a>Compiler-Fehler C2698 generiert
Die using-Deklaration für "Deklaration 1" kann nicht gleichzeitig mit den vorhandenen using-Deklaration für "Deklaration 2"  
  
 Nachdem Sie haben eine [using-Deklaration](../../cpp/using-declaration.md) für einen Datenmember, die jede Deklaration im gleichen Bereich, der den Namen verwendet, ist nicht zulässig, da nur Funktionen überladen werden können.  
  
 Im folgende Beispiel wird C2698 generiert:  
  
```  
// C2698.cpp  
struct A {  
   int x;  
};  
  
struct B {  
   int x;  
};  
  
struct C : A, B {  
   using A::x;  
   using B::x;   // C2698  
}  
```