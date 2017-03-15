---
title: "Compilerfehler C2390 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2390"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2390"
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2390
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': falscher Speicherklassen\-'Spezifizierer'  
  
 Die Speicherklasse ist für den Bezeichner im globalen Gültigkeitsbereich nicht zulässig.  Anstelle der unzulässigen Klasse wird die Standardspeicherklasse verwendet.  
  
 Mögliche Lösungen:  
  
-   Wenn der Bezeichner eine Funktion ist, deklarieren Sie ihn mit dem `extern`\-Speicher.  
  
-   Wenn der Bezeichner ein formaler Parameter oder eine lokale Variable ist, deklarieren Sie ihn mit automatischem Speicher.  
  
-   Wenn der Bezeichner eine globale Variable ist, deklarieren Sie ihn ohne Speicherklasse \(automatischer Speicher\).  
  
## Beispiel  
  
-   Im folgenden Beispiel wird C2390 generiert:  
  
```  
// C2390.cpp  
register int i;   // C2390  
  
int main() {  
   register int j;   // OK  
}  
```