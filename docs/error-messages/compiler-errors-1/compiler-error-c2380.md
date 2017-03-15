---
title: "Compilerfehler C2380 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2380"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2380"
ms.assetid: 717b1e6e-ddfe-4bac-a5f3-7f9a4dcb1572
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2380
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Typ\(en\) vor 'Bezeichner' \- \(Konstruktor mit Ergebnistyp oder unzulässige Neudefinition eines Klassennamens?\)  
  
 Durch einen Konstruktor wird ein Wert zurückgegeben bzw. der Klassenname neu definiert.  
  
 Im folgenden Beispiel wird C2326 generiert:  
  
```  
// C2380.cpp  
// compile with: /c  
class C {  
public:  
   int C();   // C2380, specifies an int return  
   int C;   // C2380, redefinition of i  
   C();   // OK  
};  
```