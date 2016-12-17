---
title: "Verwenden von additiven Operatoren"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Additive Operatoren"
  - "Operatoren [C++], Addition"
ms.assetid: 7d54841e-436d-4ae8-9865-1ac1829e6f22
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von additiven Operatoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Beispiele, welche die Additions\- und Subtraktionsoperatoren veranschaulichen, verwenden diese Deklarationen:  
  
```  
int i = 4, j;  
float x[10];  
float *px;  
```  
  
 Diese Anweisungen sind gleichwertig:  
  
```  
px = &x[4 + i];  
px = &x[4] + i;    
```  
  
 Der Wert von `i` wird mit der Länge von **float** multipliziert und zu `&x[4]` hinzugefügt.  Das Zeigerwertergebnis ist die Adresse von `x[8]`.  
  
```  
j = &x[i] - &x[i-2];  
```  
  
 In diesem Beispiel wird die Adresse des dritten Elements von `x` \(angegeben durch `x[i–2]`\) von der Adresse des fünften Elements von `x` \(angegeben durch `x[i]`\) subtrahiert.  Die Differenz wird durch die Länge eines **float** geteilt. Das Ergebnis ist der Ganzzahlwert 2.  
  
## Siehe auch  
 [C\-Operatoren \(additiv\)](../c-language/c-additive-operators.md)