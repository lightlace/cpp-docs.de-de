---
title: "Platzhaltererweiterung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
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
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Platzhaltererweiterung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Sie können Platzhalter – das Fragezeichen \(?\) und das Sternchen \(\*\) – verwenden, um Dateinamen\- und Pfadargumente in der Befehlszeile anzugeben.  
  
 Befehlszeilenargumente werden durch eine Routine behandelt, die als **\_setargv** bezeichnet wird \(oder **\_wsetargv** in der Breitzeichen\-Umgebung\). Die Routine erweitert nicht standardmäßig Platzhalter in separate Zeichenfolgen im `argv`\-Zeichenfolgenarray.  Weitere Informationen über das Aktivieren von Platzhaltererweiterung finden Sie unter [Erweitern von Platzhalterargumenten](../c-language/expanding-wildcard-arguments.md).  
  
## END Microsoft\-spezifisch  
  
## Siehe auch  
 [main: Programmstart](../cpp/main-program-startup.md)