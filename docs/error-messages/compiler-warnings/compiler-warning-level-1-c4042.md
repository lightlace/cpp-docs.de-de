---
title: "Compilerwarnung (Stufe 1) C4042"
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
  - "C4042"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4042"
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4042
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner' : Besitzt unzulässige Speicherklasse  
  
 Die angegebene Speicherklasse kann nicht mit diesem Bezeichner in diesem Kontext verwendet werden.  Der Compiler verwendet stattdessen die Standardspeicherklasse:  
  
-   `extern`, falls *Bezeichner* eine Funktion ist.  
  
-   **auto**, falls *Bezeichner* ein formaler Parameter oder eine lokale Variable ist.  
  
-   Keine Speicherklasse, falls *Bezeichner* eine globale Variable ist.  
  
 Diese Warnung kann verursacht werden, wenn eine andere Speicherklasse als **register** in einer Parameterdeklaration angegeben wird.  
  
 Im folgenden Beispiel wird C4042 generiert:  
  
```  
// C4042.cpp  
// compile with: /W1 /LD  
int func2( __declspec( thread ) int tls_i )    // C4042  
// try the following line instead  
// int func2( int tls_i )  
{  
   return tls_i;  
}  
```