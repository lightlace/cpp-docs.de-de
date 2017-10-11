---
title: Compilerfehler C2383 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2383
dev_langs:
- C++
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 20f6fa7626541f5fcd06bc2c2c513f52ec443ba4
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2383"></a>Compilerfehler C2383
"*Symbol*": Standard-Argumente dürfen nicht auf dieses Symbol  
  
 Der C++-Compiler lässt keine Standardargumente für Zeiger auf Funktionen.  
  
 Dieser Code wurde vom Visual C++-Compiler in Versionen vor Visual Studio 2005 akzeptiert, aber jetzt einen Fehler generiert. Weisen Sie für Code, der in allen Versionen von Visual C++ funktioniert einen Standardwert nicht an einen Zeiger auf Funktion-Argument.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2383 generiert und gezeigt, eine mögliche Lösung:  
  
```cpp  
// C2383.cpp  
// compile with: /c   
void (*pf)(int = 0);   // C2383  
void (*pf)(int);   // OK  
```
