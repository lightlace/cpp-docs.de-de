---
title: "Rekursionsmakros"
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
  - "Makros, Rekursion"
  - "NMAKE (Programm), Rekursionsmakros"
  - "Rekursionsmakros"
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Rekursionsmakros
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit Rekursionsmakros wird NMAKE rekursiv aufgerufen.  Rekursive Sitzungen erben aus **Tools.ini** Befehlszeilenmakros, Umgebungsvariablenmakros und Informationen.  Sie erben weder in Makefiles definierte Rückschlussregeln noch **.SUFFIXES**\-Spezifikationen und **.PRECIOUS**\-Spezifikationen.  Um Makros einer rekursiven NMAKE\-Sitzung zu übergeben, wird entweder mit **SET** eine Umgebungsvariable vor dem rekursiven Aufruf festgelegt und ein Makro im Befehl für den rekursiven Aufruf definiert, oder aber ein Makro in der Datei Tools.ini definiert  
  
|Makro|Definition|  
|-----------|----------------|  
|**MAKE**|Befehl, der ursprünglich zum Aufruf von NMAKE verwendet wurde.<br /><br /> Das $\(MAKE\)\-Makro gibt den vollständigen Pfad zu nmake.exe an.|  
|**MAKEDIR**|Aktuelles Verzeichnis beim Aufruf von NMAKE.|  
|**MAKEFLAGS**|Momentan aktive Optionen.  Zugriff über `/$(MAKEFLAGS)`.  Hinweis: \/F wird nicht verwendet.|  
  
## Siehe auch  
 [Besondere NMAKE\-Makros](../build/special-nmake-macros.md)