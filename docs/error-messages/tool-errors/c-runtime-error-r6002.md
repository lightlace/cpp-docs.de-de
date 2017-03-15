---
title: "C-Laufzeitfehler R6002 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6002"
ms.assetid: 8fbbe65a-9c43-459e-8342-e1f6d1cef7d0
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# C-Laufzeitfehler R6002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gleitkommaunterstützung ist nicht geladen  
  
 Die benötigte Gleitkommabibliothek wurde nicht verknüpft.  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Das Programm wurde mit einer Option \(z. B. **\/FPi87**\), für die ein Coprozessor erforderlich ist, kompiliert bzw. verknüpft. Das Programm wurde jedoch auf einem Computer ausgeführt, auf dem kein Coprozessor installiert ist.  
  
2.  Eine Formatzeichenfolge für eine `printf_s`\-Funktion oder `scanf_s`\-Funktion enthält die Angabe eines Gleitkommaformats, das Programm enthielt jedoch keinerlei Gleitkommawerte bzw. \-variablen.  
  
3.  Der Compiler minimiert die Größe eines Programms, indem er die Gleitkommaunterstützung nur bei Bedarf lädt.  Der Compiler kann keine Gleitkommaformate in Formatzeichenfolgen finden und lädt daher die benötigten Gleitkommaroutinen nicht.  
  
4.  Verwenden Sie ein Gleitkommaargument für das angegebene Gleitkommaformat, oder führen Sie an beliebiger Stelle im Programm eine Gleitkommazuweisung durch.  Dies bewirkt das Laden der Gleitkommaunterstützung.  
  
5.  In einem Programm mit gemischten Sprachen wurde beim Verknüpfen des Programms eine C\-Bibliothek vor einer FORTRAN\-Bibliothek angegeben.  Geben Sie die C\-Bibliothek an letzter Stelle an, und verknüpfen Sie das Programm neu.