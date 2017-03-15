---
title: "Compilerfehler C2692 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2692"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2692"
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Compilerfehler C2692
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktionsname': Der C\-Compiler erfordert vollständige Funktionen mit Prototyp mit der '\/clr'\-Option  
  
 Für die Kompilierung von .NET\-verwaltetem Code benötigt der C\-Compiler ANSI\-Funktionsdeklarationen.  Wenn eine Funktion keine Parameter annimmt, muss zusätzlich `void` explizit als Parametertyp deklariert werden.