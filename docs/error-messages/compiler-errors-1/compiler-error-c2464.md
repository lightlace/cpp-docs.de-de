---
title: "Compilerfehler C2464"
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
  - "C2464"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2464"
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2464
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': 'new' zur Reservierung eines Verweises nicht zulässig  
  
 Der Verweisbezeichner wurde mit dem Operator `new` reserviert.  Da Verweise keine Speicherobjekte sind, kann der Operator `new` keine Zeiger darauf zurückgeben.  Verwenden Sie die Standardsyntax für die Variablendeklaration, um einen Verweis zu deklarieren.  
  
 Im folgenden Beispiel wird C2464 generiert:  
  
```  
// C2464.cpp  
int main() {  
   new ( int& ir );   // C2464  
}  
```