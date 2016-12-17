---
title: "Compilerwarnung (Stufe 4) C4206"
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
  - "C4206"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4206"
ms.assetid: 3df97812-3ed7-4003-9769-057acf97ce3c
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4206
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Nicht dem Standard entsprechende Erweiterung: Übersetzungseinheit ist leer**  
  
 Nach dem Durchlauf des Präprozessors war die Datei leer.  
  
 Durch diese Erweiterung kann verhindert werden, dass der Code auf andere Compiler portierbar ist.  Sie generiert gemäß der ANSI\-Kompatibilität einen Fehler \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) und kann nur auf C\-Quellcode angewendet werden.