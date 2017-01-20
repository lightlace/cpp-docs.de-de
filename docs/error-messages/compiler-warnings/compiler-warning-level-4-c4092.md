---
title: "Compilerwarnung (Stufe 4) C4092"
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
  - "C4092"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4092"
ms.assetid: 396ae826-a892-4327-bd66-f4762376d72b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4092
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

sizeof gibt "unsigned long" zurück  
  
 Der Operand des Operators `sizeof` war sehr groß. `sizeof` hat daher **unsigned long** zurückgegeben.  Diese Warnung tritt nur bei Verwendung der Microsoft\-Erweiterungen auf \([\/Ze](../../build/reference/za-ze-disable-language-extensions.md)\).  Bei Einhaltung der ANSI\-Kompatibilität \(**\/Za**\) wird das Ergebnis stattdessen abgeschnitten.