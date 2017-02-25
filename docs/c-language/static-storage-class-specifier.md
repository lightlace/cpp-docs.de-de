---
title: "Statischer Speicherklassenspezifizierer | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Statische Speicherklassenspezifizierer"
  - "Statische Variablen, Spezifizierer"
  - "Speicherklassen, Statische"
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Statischer Speicherklassenspezifizierer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Variable, die für die interne Schicht mit dem **static**\-Speicherklassenspezifizierer deklariert wurde, hat eine globale Lebensdauer, wird jedoch nur innerhalb des Blocks angezeigt, in dem sie deklariert ist.  Bei konstanten Zeichenfolgen ist die Verwendung von **static** nützlich, da es den Mehraufwand häufiger Initialisierung in häufig aufgerufenen Funktionen verringert.  
  
## Hinweise  
 Wenn Sie nicht explizit eine **static**\-Variable initialisieren, wird sie standardmäßig auf 0 \(null\) initialisiert.  Innerhalb einer Funktion bewirkt **static**, dass Speicher zugeordnet werden, und dient als Definition.  Interne statische Variablen stellen privaten Festspeicher bereit, der nur für eine einzelne Funktion sichtbar ist.  
  
## Siehe auch  
 [Statisch](../misc/static-cpp.md)