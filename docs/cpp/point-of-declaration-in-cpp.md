---
title: "Zeitpunkt der Deklaration in C++"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zeitpunkt der Deklaration"
ms.assetid: 92ea8707-80cb-497c-b479-f907b8401859
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Zeitpunkt der Deklaration in C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es wird angenommen, dass ein Name unmittelbar nach seinem Deklarator, jedoch vor seinem \(optionalen\) Initialisierer deklariert wird.  \(Weitere Informationen über Deklaratoren finden Sie unter [Deklaratoren](assetId:///8a7b9b51-92bd-4ac0-b3fe-0c4abe771838).\)  
  
 Betrachten Sie das folgende Beispiel:  
  
```  
// point_of_declaration1.cpp  
// compile with: /W1   
double dVar = 7.0;  
int main()  
{  
   double dVar = dVar;   // C4700  
}  
```  
  
 Wenn der Punkt der Deklaration *nach* der Initialisierung lag, würde der lokale `dVar` auf 7,0 initialisiert, den Wert der globalen Variablen `dVar`.  Da dies jedoch nicht der Fall ist, wird `dVar` mit einem nicht definierten Wert initialisiert.  
  
## Siehe auch  
 [Bereich](../cpp/scope-visual-cpp.md)