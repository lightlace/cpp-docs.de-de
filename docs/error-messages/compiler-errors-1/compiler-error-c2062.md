---
title: Compilerfehler Fehler C2062 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2062
dev_langs:
- C++
helpviewer_keywords:
- C2062
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d11151a8e842796e4a5a8d45956782421daa1c70
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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