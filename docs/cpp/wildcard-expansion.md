---
title: "Platzhaltererweiterung"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "_setargv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_setargv-Funktion"
  - "Sternchen-Platzhalter"
  - "Befehlszeile, Verarbeiten von Argumenten"
  - "Befehlszeile, Platzhalter"
  - "Befehlszeilenplatzhalter"
  - "Fragezeichen, Platzhalter"
ms.assetid: 1a543398-607b-4404-93d1-45d290bde638
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Platzhaltererweiterung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Sie können Platzhalter – das Fragezeichen \(?\) und das Sternchen \(\*\) – verwenden, um Dateinamen\- und Pfadargumente in der Befehlszeile anzugeben.  
  
 Befehlszeilenargumente werden durch eine Routine behandelt, die als **\_setargv** bezeichnet wird \(oder **\_wsetargv** in der Breitzeichen\-Umgebung\). Die Routine erweitert nicht standardmäßig Platzhalter in separate Zeichenfolgen im `argv`\-Zeichenfolgenarray.  Weitere Informationen über das Aktivieren von Platzhaltererweiterung finden Sie unter [Erweitern von Platzhalterargumenten](../c-language/expanding-wildcard-arguments.md).  
  
## END Microsoft\-spezifisch  
  
## Siehe auch  
 [main: Programmstart](../cpp/main-program-startup.md)