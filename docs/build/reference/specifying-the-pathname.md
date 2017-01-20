---
title: "Festlegen des Pfadnamens"
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
  - "cl.exe-Compiler, Ausgabedateien"
  - "Namen [C++], Compilerausgabedateien"
  - "Ausgabedateien, Angeben von Pfadnamen"
ms.assetid: 7a6595ce-3383-44ae-957a-466bfa29c343
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Festlegen des Pfadnamens
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Jede Ausgabedateioption nimmt ein Argument *Pfadname* an, mit dem Pfad und Name der Ausgabedatei festgelegt werden können.  Das Argument kann einen Laufwerksnamen, ein Verzeichnis und einen Dateinamen enthalten.  Leerzeichen zwischen der Option und dem Argument sind nicht zulässig.  
  
 Wenn *Pfadname* einen Dateinamen ohne Erweiterung enthält, fügt der Compiler in der Ausgabe eine Standarderweiterung an.  Wenn *Pfadname* ein Verzeichnis, aber keinen Dateinamen enthält, erstellt der Compiler eine Datei mit einem Standardnamen im angegebenen Verzeichnis.  Der Standardname setzt sich aus dem Basisnamen der Quelldatei und einer Standarderweiterung zusammen, die auf dem Typ der Ausgabedatei basiert.  Wenn das Argument *Dateiname* ganz weggelassen wird, erstellt der Compiler eine Datei mit einem Standardnamen in einem Standardverzeichnis.  
  
 Alternativ dazu kann das Argument *Pfadname* anstatt eines Dateinamens einen Gerätenamen \(AUX, CON, PRN oder NUL\) enthalten.  Setzen Sie zwischen der Option und dem Gerätenamen kein Leerzeichen und keinen Doppelpunkt als Teil des Gerätenamens.  
  
|Gerätename|Bedeutung|  
|----------------|---------------|  
|AUX|Externes Gerät|  
|CON|Konsole|  
|PRN|Drucker|  
|NUL|Nullgerät \(keine Datei erstellt\)|  
  
## Beispiel  
 Die folgende Befehlszeile sendet eine MAP\-Datei an den Drucker:  
  
```  
CL /FmPRN HELLO.CPP  
```  
  
## Siehe auch  
 [\/F\-Optionen \(Ausgabedateioptionen\)](../../build/reference/output-file-f-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)