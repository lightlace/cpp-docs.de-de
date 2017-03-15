---
title: "Compilerfehler C2433 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2433"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2433"
ms.assetid: 7079fedd-6059-4125-82ef-ebe275f1f9d1
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C2433
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': 'Modifizierer' bei der Deklaration von Daten nicht zulässig  
  
 Die Modifizierer `friend`, `virtual` und `inline` können nicht für Datendeklarationen verwendet werden.  
  
## Beispiel  
 Im folgenden Beispiel wird C2433 generiert.  
  
```  
// C2433.cpp  
class C{};  
  
int main() {  
   inline C c;   // C2433  
}  
```