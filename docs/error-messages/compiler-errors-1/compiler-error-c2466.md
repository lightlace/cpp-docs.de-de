---
title: "Compilerfehler C2466"
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
  - "C2466"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2466"
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2466
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Reservierung eines Arrays der konstanten Größe 0 nicht möglich  
  
 Es wurde ein Array der Größe 0 reserviert oder deklariert.  Der konstante Ausdruck für die Arraygröße muss einer ganzen Zahl größer 0 entsprechen.  Eine Arraydeklaration mit einem Nullindex ist nur für Klassen\-, Struktur\- oder Unionmember zulässig, und auch nur dann, wenn die Microsoft\-Erweiterungen \([\/Ze](../../build/reference/za-ze-disable-language-extensions.md)\) aktiviert sind.  
  
 Im folgenden Beispiel wird C2466 generiert:  
  
```  
// C2466.cpp  
// compile with: /c  
int i[0];   // C2466  
int j[1];   // OK  
char *p;  
```