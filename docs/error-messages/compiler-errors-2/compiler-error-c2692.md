---
title: "Compilerfehler C2692"
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
  - "C2692"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2692"
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2692
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktionsname': Der C\-Compiler erfordert vollständige Funktionen mit Prototyp mit der '\/clr'\-Option  
  
 Für die Kompilierung von .NET\-verwaltetem Code benötigt der C\-Compiler ANSI\-Funktionsdeklarationen.  Wenn eine Funktion keine Parameter annimmt, muss zusätzlich `void` explizit als Parametertyp deklariert werden.