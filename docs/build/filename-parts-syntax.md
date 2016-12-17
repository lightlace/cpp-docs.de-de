---
title: "Syntax f&#252;r Dateinamenteile"
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
  - "Syntax für Teile von Dateinamen in NMAKE"
  - "NMAKE (Programm), Syntax"
  - "Syntax, Teile von Dateinamen"
ms.assetid: 48fe38e0-3f3b-40e6-894c-330ee775a656
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Syntax f&#252;r Dateinamenteile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Syntax für Teile von Dateinamen in Befehlen repräsentiert Komponenten des ersten abhängigen Dateinamens \(wobei es sich um eine implizierte abhängige Datei handeln kann\).  Bei Komponenten von Dateinamen handelt es sich um das Laufwerk, den Pfad, den Basisnamen und die angegebene Erweiterung der Datei. Die Angabe auf dem Datenträger ist dabei nicht maßgebend.  Mit **%s** kann der vollständige Dateiname repräsentieren werden.  Mit %&#124;\[*parts*\]F \(ein senkrechter Strich befindet sich hinter dem Prozentzeichen\) können Teile des Dateinamen repräsentiert werden. *parts* kann null oder mehrere der folgenden Buchstaben in beliebiger Reihenfolge enthalten.  
  
|Buchstabe|**Beschreibung**|  
|---------------|----------------------|  
|Kein Buchstabe|Vollständiger Name \(entspricht **%s**\)|  
|**d**|Laufwerk|  
|**p**|Pfad|  
|**f**|Basisname der Datei|  
|**e**|Dateierweiterung|  
  
 Lautet z. B. der Dateiname c:\\Prog.exe, entspricht:  
  
-   **%s** der Zeichenfolge **c:\\prog.exe**  
  
-   %&#124;F der Zeichenfolge c:\\prog.exe  
  
-   %&#124;dF der Zeichenfolge c  
  
-   %&#124;pF der Zeichenfolge c:\\  
  
-   %&#124;fF der Zeichenfolge prog  
  
-   %&#124;eF der Zeichenfolge exe  
  
## Siehe auch  
 [Befehle in einem Makefile](../build/commands-in-a-makefile.md)