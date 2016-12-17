---
title: "Compilerwarnung (Stufe 3) C4414"
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
  - "C4414"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4414"
ms.assetid: bc81d3ad-55dc-4a6b-a6f2-ec0ef38347df
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 3) C4414
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': short\-Sprung zur Funktion konvertiert in near  
  
 short\-Sprünge erzeugen eine kompakte Anweisung, die zu einer Adresse innerhalb eines begrenzten Bereichs der Anweisung verzweigt wird.  Die Anweisung enthält ein short\-Offset, das die Distanz zwischen der Sprung\- und der Zieladresse, d. h. der Funktionsdefinition, darstellt.  Während der Verknüpfung kann eine Funktion verschoben werden oder Link\-Time\-Optimierungen unterliegen, wodurch die Funktion aus dem von einem short\-Offset erreichbaren Bereich verschoben wird.  Der Compiler muss einen speziellen Datensatz für den Sprung erzeugen. Der Sprung erfordert, dass die jmp\-Anweisung entweder NEAR oder FAR ist.  Die Konvertierung wurde vom Compiler durchgeführt.  
  
 Der folgende Code generiert z. B. C4414:  
  
```  
// C4414.cpp  
// compile with: /W3 /c  
// processor: x86  
int DoParityEven();  
int DoParityOdd();  
unsigned char global;  
int __declspec(naked) DoParityEither()  
{  
   __asm  
   {  
      test global,0  
      jpe SHORT DoParityEven  // C4414  
      jmp SHORT DoParityOdd   // C4414  
   }  
}  
```