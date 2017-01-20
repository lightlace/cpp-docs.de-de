---
title: "Compilerfehler C2632"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2632"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2632"
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
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