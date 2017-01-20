---
title: "Compilerfehler C2585"
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
  - "C2585"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2585"
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2585
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Explizite Konvertierung in 'Typ' ist mehrdeutig  
  
 Die Typkonvertierung kann mehrere Ergebnisse ergeben.  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Konvertierung von einem Klassen\- oder Strukturtyp, der auf Mehrfachvererbung basiert.  Wenn der Typ dieselbe Basisklasse mehrfach erbt, müssen die Konvertierungsfunktion oder der Konvertierungsoperator mittels der Bereichsauflösung \(`::`\) festlegen, welche der geerbten Klassen in der Konvertierung verwendet werden sollen.  
  
2.  Ein Konvertierungsoperator und ein Konstruktor wurden durch dieselbe Konvertierung definiert.