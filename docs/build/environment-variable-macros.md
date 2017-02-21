---
title: "Makros von Umgebungsvariablen | Microsoft Docs"
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
  - "Umgebungsvariablen, Makros in NMAKE"
  - "Makros, Umgebungsvariable"
  - "NMAKE (Programm), Umgebungvariablenmakros"
ms.assetid: f8e96635-0906-47b0-9f56-12a6fdf5e347
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Makros von Umgebungsvariablen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

NMAKE erbt Makrodefinitionen für Umgebungsvariablen, die vor dem Beginn einer Sitzung vorhanden sind.  Wenn eine Umgebungsvariable in der Betriebssystemumgebung festgelegt wurde, ist diese als NMAKE\-Makro verfügbar.  Die geerbten Namen werden in Großbuchstaben konvertiert.  Die Vererbung erfolgt vor dem Präprozessorlauf.  Mit der \/E\-Option werden Makros durch Umgebungsvariablenmakros mit dem gleichen Namen im Makefile überschrieben.  
  
 Umgebungsvariablenmakros können in der Sitzung neu definiert werden, wodurch die entsprechende Umgebungsvariable geändert wird.  Umgebungsvariablen können auch über den **SET**\-Befehl geändert werden.  Umgebungsvariablen, die in einer Sitzung mit dem **SET**\-Befehl geändert wurden, ändern jedoch nicht das entsprechende Makro.  
  
 Beispiel:  
  
```  
PATH=$(PATH);\nonesuch  
  
all:  
    echo %PATH%  
```  
  
 In diesem Beispiel ändert die `PATH`\-Änderung die entsprechende Umgebungsvariable `PATH`. Es wird `\nonesuch` an den Pfad angefügt.  
  
 Wenn eine Umgebungsvariable als Zeichenfolge, die in einem Makefile syntaktisch falsch ist, definiert ist, wird kein Makro erstellt und keine Warnung generiert.  Enthält der Wert einer Variablen ein Dollarzeichen \(`$`\), wird diese von NMAKE als Beginn eines Makroaufrufs interpretiert.  Das Verwenden des Makros kann unerwartetes Verhalten verursachen.  
  
## Siehe auch  
 [Besondere NMAKE\-Makros](../build/special-nmake-macros.md)