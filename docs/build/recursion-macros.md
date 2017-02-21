---
title: "Rekursionsmakros | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Makros, Rekursion"
  - "NMAKE (Programm), Rekursionsmakros"
  - "Rekursionsmakros"
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
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