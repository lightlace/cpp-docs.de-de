---
title: Compilerwarnung (Stufe 1) C4584 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4584
dev_langs:
- C++
helpviewer_keywords:
- C4584
ms.assetid: ad86582f-cb8c-4d21-8c4c-a6c800059e25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df3f92142fe42451ca7ae8272463d9347a263121
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4584"></a>Compilerwarnung (Stufe 1) C4584
'Klasse1': Basisklasse 'Klasse2' ist bereits eine Basisklasse "class3"  
  
 Die Klasse, die Sie definiert erbt von zwei Klassen, von denen aus den anderen erbt. Zum Beispiel:  
  
```  
// C4584.cpp  
// compile with: /W1 /LD  
class A {  
};  
  
class B : public A {  
};  
  
class C : public A, public B { // C4584  
};  
```  
  
 In diesem Fall würde eine Warnung für Klasse C ausgegeben werden, weil es erbt sowohl von Klasse A und B, der auch von Klasse a erbt-Klasse Diese Warnung dient als eine Erinnerung, Sie die Verwendung von Elementen aus dieser Basisklassen vollständig qualifizieren müssen oder aufgrund der Mehrdeutigkeit hinsichtlich der, die Klassenmember Sie finden ein Compilerfehler generiert werden.