---
title: "Compilerfehler C2612"
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
  - "C2612"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2612"
ms.assetid: 6faacfd6-4455-41a2-808e-0f6799f84d6d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2612
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Abschließendes 'Zeichen' in Initialisierungsliste für Basisklasse\/Member nicht zulässig  
  
 Hinter der letzten Basisklasse oder dem letzten Member in einer Initialisierungsliste steht ein Zeichen.  
  
 Im folgenden Beispiel wird C2612 generiert:  
  
```  
// C2612.cpp  
class A {  
public:  
   int i;  
   A( int ia ) : i( ia ) + {};   // C2612  
};  
```