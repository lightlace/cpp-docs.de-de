---
title: Compiler-Fehler C2602 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2602
dev_langs: C++
helpviewer_keywords: C2602
ms.assetid: 6c07a40e-537e-4954-b5c5-1e0e58fe1952
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9bd53ce47aeb31022e042b515409a98b087c6813
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2602"></a>Compiler-Fehler C2602 generiert
'class:: Identifier' ist kein Member einer Basisklasse von 'Klasse'  
  
 `Identifier`kann nicht zugegriffen werden, da es sich nicht um einen von einer Basisklasse geerbten Member ist.  
  
 Im folgende Beispiel wird C2602 generiert:  
  
```  
// C2602.cpp  
// compile with: /c  
struct X {  
   int x;  
};  
struct A {  
   int a;  
};  
struct B : public A {  
   X::x;   // C2602 B is not derived from X  
   A::a;   // OK  
};  
```