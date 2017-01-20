---
title: "NMAKE: Schwerwiegender Fehler U1059"
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
  - "U1059"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1059"
ms.assetid: b21d9198-9c63-40d0-b589-80e17294ce24
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE: Schwerwiegender Fehler U1059
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Syntaxfehler: "}" fehlt im abhängigen Element  
  
 Ein Suchpfad für eine abhängige Datei wurde falsch angegeben.  Entweder ist ein Leerzeichen im Pfad enthalten, oder die schließende Klammer \(**}**\) fehlt.  
  
 Die Syntax zur Verzeichnisangabe für eine abhängige Datei lautet:  
  
 **{**   
 ***Verzeichnisse* }abhängige Datei**  
  
 Hierbei wird in `directories` ein Pfad oder mehrere Pfade, die jeweils durch ein Semikolon \(;\) getrennt sind, angegeben.  Es sind keine Leerzeichen zulässig.  
  
 Falls ein Teil eines Suchpfades oder ein vollständiger Suchpfad von einem Makro ersetzt wird, stellen Sie sicher, dass keine Leerzeichen in der Makroerweiterung vorhanden sind.