---
title: "Statischer Speicherklassenspezifizierer"
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
  - "Statische Speicherklassenspezifizierer"
  - "Statische Variablen, Spezifizierer"
  - "Speicherklassen, Statische"
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Statischer Speicherklassenspezifizierer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Variable, die für die interne Schicht mit dem **static**\-Speicherklassenspezifizierer deklariert wurde, hat eine globale Lebensdauer, wird jedoch nur innerhalb des Blocks angezeigt, in dem sie deklariert ist.  Bei konstanten Zeichenfolgen ist die Verwendung von **static** nützlich, da es den Mehraufwand häufiger Initialisierung in häufig aufgerufenen Funktionen verringert.  
  
## Hinweise  
 Wenn Sie nicht explizit eine **static**\-Variable initialisieren, wird sie standardmäßig auf 0 \(null\) initialisiert.  Innerhalb einer Funktion bewirkt **static**, dass Speicher zugeordnet werden, und dient als Definition.  Interne statische Variablen stellen privaten Festspeicher bereit, der nur für eine einzelne Funktion sichtbar ist.  
  
## Siehe auch  
 [Statisch](../misc/static-cpp.md)