---
title: Compilerfehler C2383 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2383
dev_langs:
- C++
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 81624ccd7f4857cb2f7d8474d393a9743ab1a2b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33196492"
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