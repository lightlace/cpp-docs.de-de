---
title: "Schwerwiegender Fehler C1026 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1026"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1026"
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Schwerwiegender Fehler C1026
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stapelüberlauf im Parser, Programm zu komplex  
  
 Aufgrund des für die Programmanalyse erforderlichen Speicherplatzes wurde ein Überlauf des Compilerstapels verursacht.  
  
 Verringern Sie die Komplexität der Ausdrücke wie folgt:  
  
-   Verringern Sie die Schachtelungstiefe in `for`\-Anweisungen und `switch`\-Anweisungen.  Definieren Sie tief geschachtelte Anweisungen in separaten Funktionen.  
  
-   Teilen Sie lange Ausdrücke, die Kommaoperatoren oder Funktionsaufrufe enthalten, auf.