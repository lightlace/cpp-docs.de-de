---
title: "Compilerwarnung (Stufe 1) C4129 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4129"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4129"
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4129
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Zeichen': Unbekanntes Zeichen in Escape\-Sequenz  
  
 Das in einer Zeichen\- oder Zeichenfolgenkonstante auf einen umgekehrten Schrägstrich \(\\\) folgende `character` wird nicht als gültige Escape\-Sequenz erkannt.  Der umgekehrte Schrägstrich wird ignoriert und nicht ausgegeben.  Das Zeichen hinter dem umgekehrten Schrägstrich wird ausgegeben.  
  
 Um einen einfachen umgekehrten Schrägstrich auszugeben, geben Sie diesen doppelt an \(\\\\\).  
  
 Im C\+\+\-Standard, in Abschnitt 2.13.2, werden Escape\-Sequenzen behandelt.  
  
 Im folgenden Beispiel wird C4129 generiert:  
  
```  
// C4129.cpp  
// compile with: /W1  
int main() {  
   char array1[] = "\/709";   // C4129  
   char array2[] = "\n709";   // OK  
}  
```