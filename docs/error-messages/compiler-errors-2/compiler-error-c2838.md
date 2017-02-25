---
title: "Compilerfehler C2838 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2838"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2838"
ms.assetid: 176b2ad6-7a84-4019-b97e-328866054457
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2838
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Member': Unzulässiger gekennzeichneter Name in Memberdeklaration  
  
 Eine Klasse, Struktur oder Union verwendet einen voll gekennzeichneten Namen, um einen Member einer anderen Klasse, Struktur oder Union erneut zu deklarieren.  
  
 Im folgenden Beispiel wird C2838 generiert:  
  
```  
// C2838.cpp  
// compile with: /c  
class Bellini {  
public:  
    void Norma();  
};  
  
class Bottesini {  
   Bellini::Norma();  // C2838  
};  
```