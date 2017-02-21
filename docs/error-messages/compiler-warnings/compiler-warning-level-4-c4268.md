---
title: "Compilerwarnung (Stufe 4) C4268 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4268"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4268"
ms.assetid: d0511e80-904f-4ee1-b4d7-39b5c0bd8234
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 4) C4268
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Die durch den vom Compiler generierten Standardkonstruktor initialisierten statischen\/globalen Daten vom Typ 'const' füllen das Objekt mit Nullen  
  
 Eine globale oder statische Instanz vom Typ **const** einer nicht trivialen Klasse wird mit einem vom Compiler erzeugten Standardkonstruktor initialisiert.  
  
## Beispiel  
  
```  
// C4268.cpp  
// compile with: /c /LD /W4  
class X {  
public:  
   int m_data;  
};  
  
const X x1;   // C4268  
```  
  
 Da diese Instanz der Klasse den Typ **const** hat, kann der Wert von `m_data` nicht geändert werden.