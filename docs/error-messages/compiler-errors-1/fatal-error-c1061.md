---
title: "Schwerwiegender Fehler C1061"
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
  - "C1061"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1061"
ms.assetid: 9366c0bc-96e0-4967-aa7d-4ebf098de806
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1061
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compilerlimit: Blöcke zu tief geschachtelt  
  
 Die Schachtelungstiefe für Codeblöcke überschreitet die maximale Anzahl von 128 Ebenen.  Hierbei handelt es sich um einen festen Grenzwert im Compiler im 32\-Bit\- und 64\-Bit\-Toolsatz von C und C\+\+.  Alle Verhaltensweisen, durch die ein Gültigkeitsbereich oder ein Block erstellt wird, können die Anzahl der Schachtelungsebenen erhöhen.  So können z. B. Namespaces, Direktiven, Präprozessorerweiterungen, Vorlagenerweiterungen, Ausnahmebehandlungen, Schleifenkonstrukte und elseif\-Klauseln zur Erhöhung der vom Compiler erkannten Schachtelungsebene beitragen.  
  
 Um diesen Fehler zu beheben, müssen Sie den Code umgestalten.  In jedem Fall ist tief geschachtelter Code nur schwer nachzuvollziehen.  Eine Reduzierung der Schachtelungsebenen des Codes verbessert die Codequalität und vereinfacht die Verwaltung.  Gliedern Sie daher tief geschachtelten Code in Funktionen auf, die in ihrem ursprünglichen Kontext aufgerufen werden.  Beschränken Sie die Anzahl von Schleifen oder verketteten elseif\-Klauseln innerhalb eines Blocks.