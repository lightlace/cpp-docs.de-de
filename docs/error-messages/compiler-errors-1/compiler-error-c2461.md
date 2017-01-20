---
title: "Compilerfehler C2461"
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
  - "C2461"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2461"
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2461
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse': Formale Parameter für Konstruktorsyntax fehlt  
  
 Für den Konstruktor der Klasse wurden keine formalen Parameter angegeben.  In der Deklaration eines Konstruktors muss ein formaler Parameter angegeben werden. \(Die Liste kann leer sein.\)  
  
 Fügen Sie hinter *Klasse*`::`*Klasse* ein Klammernpaar ein.  
  
 Im folgenden Beispiel wird C2461 generiert:  
  
```  
// C2461.cpp  
// compile with: /c  
class C {  
   C::C;   // C2461  
   C::C();   // OK  
};  
```