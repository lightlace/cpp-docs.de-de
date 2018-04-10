---
title: Compilerfehler Fehler C2632 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C2632
dev_langs:
- C++
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 03a6d75ab9af6cd45ef982ff9d2e12640266c1b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2632"></a>Compilerfehler Fehler C2632
"Typ1", gefolgt von "Typ2" ist nicht zulässig  
  
 Dieser Fehler kann verursacht werden, wenn es zwischen zwei Typspezifizierern Code vorhanden ist.  
  
 Im folgenden Beispiel wird C2632 generiert:  
  
```  
// C2632.cpp  
int float i;   // C2632  
```  
  
 Dieser Fehler kann außerdem infolge einer konformitätsverbesserung generiert werden, die für Visual Studio .NET 2003 durchgeführt wurde. `bool`ist jetzt ein richtiger Typ. In früheren Versionen `bool` wurde eine Typdefinition, und Bezeichner konnten mit diesem Namen erstellt.  
  
 Im folgenden Beispiel wird C2632 generiert:  
  
```  
// C2632_2.cpp  
// compile with: /LD  
void f(int bool);   // C2632  
```  
  
 Benennen Sie den Bezeichner, um diesen Fehler zu beheben, damit der Code in der Visual Studio .NET 2003 und die Visual Studio .NET Versionen von Visual C++ gültig ist.