---
title: Compiler-Fehler C2698 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2698
dev_langs:
- C++
helpviewer_keywords:
- C2698
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c466e39702f1e408ad96d79c16c4a5953fa373f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33233816"
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