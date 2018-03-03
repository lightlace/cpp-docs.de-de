---
title: Compiler-Fehler C2084 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2084
dev_langs:
- C++
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf9e0888e0f959d77198efe036c0234c985ea365
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2084"></a>Compiler-Fehler C2084 generiert
Funktion "*Funktion*' weist bereits einen Text  
  
 Die Funktion wurde bereits definiert.  
  
 In Versionen von Visual C++ vor Visual Studio 2002  
  
-   Obwohl zusätzlichen Definitionen nie verfügbar wäre, würde der Compiler mehrere vorlagenspezialisierungen, der in der gleichen tatsächlichen Typ aufgelöst akzeptieren. Der Compiler erkennt jetzt diese mehrere Definitionen.  
  
-   `__int32`und `int` wurden als separate Typen behandelt. Der Compiler jetzt behandelt `__int32` als Synonym für `int`. Dies bedeutet, dass der Compiler mehrere Definitionen erkennt, wenn eine Funktion, auf beiden überladen ist `__int32` und `int` eine Fehlermeldung ausgegeben.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2084 generiert:  
  
```cpp  
// C2084.cpp  
void Func(int);  
void Func(int) {}   // define function  
void Func(int) {}   // C2084 second definition  
```  
  
Um diesen Fehler zu beheben, entfernen Sie das doppelte Definition:  
  
```  
// C2084b.cpp  
// compile with: /c  
void Func(int);  
void Func(int) {}  
```