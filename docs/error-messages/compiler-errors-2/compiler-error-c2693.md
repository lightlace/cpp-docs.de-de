---
title: "Compilerfehler C2693 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2693"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2693"
ms.assetid: b7364ca8-b6be-48c0-97d6-6029787fb171
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# Compilerfehler C2693
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' : unzulässiger Vergleich für Verweise auf ein verwaltetes oder WinRT\-Array  
  
 Sie können ein verwaltetes oder WinRT\-Array nicht für jede Art von Ungleichheit testen.  Sie können beispielsweise testen, um festzustellen, ob verwaltete Arrays gleich sind, aber Sie können nicht testen, um festzustellen, ob ein Array größer oder kleiner als ein anderes Array ist.  
  
 **Verwaltete Erweiterungen für C\+\+**  
  
 Sie können ein [\_\_gc](../../misc/gc.md)\-Array nicht für jede Art von Ungleichheit testen.  Sie können beispielsweise testen, um festzustellen, ob verwaltete Arrays gleich sind, aber Sie können nicht testen, um festzustellen, ob ein Array größer oder kleiner als ein anderes Array ist.  
  
 Im folgenden Beispiel wird C2693 generiert:  
  
```  
// C2693b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
int func3(int a __gc[], int b __gc[]) {  
   return a < b;    // C2693  
}  
int func1(int a __gc[], int b __gc[]) {  
   return a != b;   // OK  
}  
  
int func2(int a __gc[], int b __gc[]) {  
   return a == b;   // OK  
}  
```