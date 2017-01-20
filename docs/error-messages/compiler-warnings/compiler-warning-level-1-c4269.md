---
title: "Compilerwarnung (Stufe 1) C4269"
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
  - "C4269"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4269"
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4269
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Automatische Daten vom Typ 'const', die mit dem vom Compiler generierten Standardkonstruktor initialisiert werden, verursachen unzuverlässige Ergebnisse  
  
 Eine automatische Instanz vom Typ **const** einer nicht trivialen Klasse wird mit einem vom Compiler erzeugten Standardkonstruktor initialisiert.  
  
## Beispiel  
  
```  
// C4269.cpp  
// compile with: /c /LD /W1  
class X {  
public:  
   int m_data;  
};  
  
void g() {  
   const X x1;   // C4269  
};  
```  
  
 Da diese Instanz der Klasse auf dem Stapel generiert wird, kann der Anfangswert von `m_data` ein beliebiger Wert sein.  Da es eine Instanz vom Typ **const** ist, kann der Wert von `m_data` nicht geändert werden.