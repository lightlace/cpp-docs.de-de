---
title: Compiler-Fehler C2698 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2698
dev_langs: C++
helpviewer_keywords: C2698
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 654367e882b16c18cc4bd58c339d61c653dc68e9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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