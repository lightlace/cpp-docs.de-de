---
title: "Ausdr&#252;cke f&#252;r den Pr&#228;prozessorlauf eines Makefiles"
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
helpviewer_keywords: 
  - "Ausdrücke [C++], Makefile-Vorverarbeitung"
  - "Makefiles, Vorverarbeiten"
  - "Vorverarbeiten von Makefiles"
ms.assetid: 37f0f413-97e0-452c-a83f-3c9002c44c92
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Ausdr&#252;cke f&#252;r den Pr&#228;prozessorlauf eines Makefiles
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`constantexpression` besteht bei \!IF\-Direktiven und \!ELSE IF\-Direktiven aus Ganzzahlkonstanten \(in dezimaler Notation oder in der Notation der Programmiersprache C\), Zeichenfolgenkonstanten oder Befehlen.  Ausdrücke können mit Klammern gruppiert werden.  Von Ausdrücken werden 32\-Bit\-Ganzzahlen mit Vorzeichen entsprechend der C\-Konvention verwendet. Die Zahlen werden in der 32\-Bit\-Zweierkomplementdarstellung im Bereich von –2147483648 bis 2147483647 ausgedrückt.  
  
 Operatoren, die für Konstantenwerte, Exitcodes von Befehlen, Zeichenfolgen, Makros sowie Pfade des Dateisystems angewendet werden, können in Ausdrücke eingesetzt werden.  
  
## Worüber möchten Sie mehr erfahren?  
 [Operatoren für den Präprozessorlauf eines Makefiles](../build/makefile-preprocessing-operators.md)  
  
 [Ausführen eines Programms im Präprozessorlauf](../build/executing-a-program-in-preprocessing.md)  
  
## Siehe auch  
 [Präprozessorlauf eines Makefiles](../build/makefile-preprocessing.md)