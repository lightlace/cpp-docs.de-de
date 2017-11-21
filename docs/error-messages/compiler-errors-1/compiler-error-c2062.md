---
title: Compilerfehler Fehler C2062 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2062
dev_langs: C++
helpviewer_keywords: C2062
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 775923345052aba99b05f708c417b8bed267119b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2062"></a>Compilerfehler Fehler C2062
Typ "Type" Unerwarteter  
  
 Nicht erwartet der Compiler hat einen Typnamen.  
  
 Im folgenden Beispiel wird C2062 generiert:  
  
```  
// C2062.cpp  
// compile with: /c  
struct A {  : int l; };   // C2062  
struct B { private: int l; };   // OK  
```  
  
 C2062 kann auch auftreten, wenn der Compiler nicht definierte Typen in einem Konstruktor Parameterliste findet. Wenn der Compiler einen undefinierten (falsch)? Typ erkennt, wird es der Konstruktor ist ein Ausdruck, und C2062. Verwenden Sie nur definierte Typen in einer Konstruktorparameterliste, um zu beheben.