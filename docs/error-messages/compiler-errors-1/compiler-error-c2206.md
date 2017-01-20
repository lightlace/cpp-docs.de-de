---
title: "Compilerfehler C2206"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C2206"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2206"
ms.assetid: d7fba68b-aa28-4885-a9a0-27107358f066
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2206
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„function“: typedef kann nicht für die Definition einer Funktion verwendet werden.  
  
 Ein `typedef`\-Element wird verwendet, um einen Funktionstyp zu definieren.  
  
 Das folgende Beispiel generiert C2206:  
  
```  
// C2206.cpp typedef int functyp(); typedef int MyInt; functyp func1 {};   // C2206 int main() { MyInt i = 0;   // OK }  
```