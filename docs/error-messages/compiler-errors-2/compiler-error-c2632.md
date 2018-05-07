---
title: Compilerfehler Fehler C2632 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2632
dev_langs:
- C++
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c3bc07c404a1f4d667045fdfea24009e7d20ad69
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2632"></a>Compilerfehler Fehler C2632
"Typ1", gefolgt von "Typ2" ist nicht zulässig  
  
 Dieser Fehler kann verursacht werden, wenn es zwischen zwei Typspezifizierern Code vorhanden ist.  
  
 Im folgenden Beispiel wird C2632 generiert:  
  
```  
// C2632.cpp  
int float i;   // C2632  
```  
  
 Dieser Fehler kann außerdem infolge einer konformitätsverbesserung generiert werden, die für Visual Studio .NET 2003 durchgeführt wurde. `bool` ist jetzt ein richtiger Typ. In früheren Versionen `bool` wurde eine Typdefinition, und Bezeichner konnten mit diesem Namen erstellt.  
  
 Im folgenden Beispiel wird C2632 generiert:  
  
```  
// C2632_2.cpp  
// compile with: /LD  
void f(int bool);   // C2632  
```  
  
 Benennen Sie den Bezeichner, um diesen Fehler zu beheben, damit der Code in der Visual Studio .NET 2003 und die Visual Studio .NET Versionen von Visual C++ gültig ist.