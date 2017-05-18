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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: faa2aa2c29ea34009f0812a3796d450a6877ca48
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

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
