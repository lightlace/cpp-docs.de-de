---
title: "Compilerfehler C2267 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2267"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2267"
ms.assetid: ea63bebb-6208-4367-8440-39be07f9c360
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2267
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Statische Funktionen mit Blockbereich sind unzulässig  
  
 Eine lokale Funktion wurde mit dem Typ `static` deklariert.  Statische Funktionen müssen über einen globalen Gültigkeitsbereich verfügen.  
  
 Im folgenden Beispiel wird C2267 generiert:  
  
```  
// C2267.cpp  
static int func2();   // OK  
int main() {  
    static int func1();   // C2267  
}  
```