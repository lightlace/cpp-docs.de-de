---
title: "Linkertoolfehler LNK1245"
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
  - "LNK1245"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1245"
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK1245
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Es wurde ein ungültiges Subsystem 'Subsystem' angegeben; \/SUBSYSTEM muss WINDOWS, WINDOWSCE oder CONSOLE sein  
  
 Es wurde [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) verwendet, um das Objekt zu kompilieren, während eine der folgenden Bedingungen zutraf:  
  
-   Ein benutzerdefinierter Einstiegspunkt \([\/ENTRY](../../build/reference/entry-entry-point-symbol.md)\) wurde definiert, sodass der Linker kein Subsystem ableiten konnte.  
  
-   Es wurde ein Wert an die [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md)\-Linkeroption übergeben, der für \/clr\-Objekte nicht gültig ist.  
  
 In beiden Fällen kann das Problem durch Angabe eines gültigen Werts in der \/SUBSYSTEM\-Linkeroption behoben werden.