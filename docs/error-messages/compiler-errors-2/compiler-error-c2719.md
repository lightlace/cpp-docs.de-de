---
title: "Compilerfehler C2719"
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
  - "C2719"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2719"
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2719
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'parameter': formeller Parameter mit \_\_declspec\(align\('\#'\)\) wird nicht ausgerichtet  
  
 Der [align](../../cpp/align-cpp.md)`__declspec` \-Modifikator ist in Funktionsparametern nicht zulässig.  Die Funktionsparameterausrichtung wird durch die verwendete Aufrufkonvention gesteuert.  Weitere Informationen finden Sie unter [Aufrufkonventionen](../../cpp/calling-conventions.md).  
  
 Im folgenden Beispiel wird C2719 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2719.cpp  
void func(int __declspec(align(32)) i);   // C2719  
// try the following line instead  
// void func(int i);  
```