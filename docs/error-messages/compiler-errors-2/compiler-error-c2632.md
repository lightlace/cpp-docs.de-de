---
title: "Compilerfehler C2632 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2632"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2632"
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C2632
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ1' gefolgt von 'Typ2' ist unzulässig  
  
 Dieser Fehler kann verursacht werden, wenn zwischen zwei Typspezifizierern Code fehlt.  
  
 Im folgenden Beispiel wird C2632 generiert:  
  
```  
// C2632.cpp  
int float i;   // C2632  
```  
  
 Dieser Fehler kann auch aufgrund einer Verbesserung der Compilerkonformität in Visual Studio .NET 2003 ausgegeben werden.  `bool` ist jetzt ein richtiger Typ.  In früheren Versionen war `bool` eine Typdefinition, und Bezeichner konnten mit diesem Namen erstellt werden.  
  
 Im folgenden Beispiel wird C2632 generiert:  
  
```  
// C2632_2.cpp  
// compile with: /LD  
void f(int bool);   // C2632  
```  
  
 Um diesen Fehler zu beheben und die Gültigkeit des Codes sowohl in der Visual Studio .NET 2003\-Version als auch in der Visual Studio .NET\-Version von Visual C\+\+ zu gewährleisten, benennen Sie den Bezeichner um.