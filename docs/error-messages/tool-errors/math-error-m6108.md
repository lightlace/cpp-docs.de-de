---
title: "Mathematischer Fehler M6108 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "M6108"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6108"
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Mathematischer Fehler M6108
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Quadratwurzel  
  
 Der Operand einer Quadratwurzeloperation war negativ.  
  
 Das Programm wird mit Exitcode 136 beendet.  
  
> [!NOTE]
>  Die `sqrt`\-Funktion in der C\-Laufzeitbibliothek und die FORTRAN\-Funktion **SQRT** generieren diesen Fehler nicht.  Die sqrt\-Funktion von C überprüft den übergebenen Parameter vor der Ausführung der Operation und liefert im Falle eines negativen Operanden einen Fehlerwert.  Die **SQRT**\-Funktion von FORTRAN generiert stattdessen den DOMAIN\-Fehler [M6201](../../error-messages/tool-errors/math-error-m6201.md).