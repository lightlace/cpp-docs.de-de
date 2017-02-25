---
title: "LINK-Befehlsdateien | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "link"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Befehlsdateien [C++]"
  - "Befehlsdateien [C++], LINK"
  - "LINK-Tool [C++]"
  - "LINK-Tool [C++], Befehlszeilensyntax"
  - "Syntax, LINK-Befehlsdateien"
  - "Textdateien, Übergeben von Argumenten an LINK"
ms.assetid: 7154511c-32b9-4e5b-a515-3922fa9de48e
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# LINK-Befehlsdateien
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sie können Argumente in der Befehlszeile in Form einer Befehlsdatei an **LINK** übergeben.  Verwenden Sie beim Angeben einer Befehlsdatei für den Linker die folgende Syntax:  
  
```  
LINK @commandfile  
```  
  
 *Commandfile* ist der Name einer Textdatei.  Zwischen dem @\-Zeichen und dem Dateinamen sind keine Leerzeichen oder Tabulatorzeichen erlaubt.  Da es keine Standarddateierweiterung gibt, müssen Sie den vollständigen Dateinamen inklusive Erweiterung angeben.  Platzhalter können nicht verwendet werden.  Sie können mit dem Dateinamen einen absoluten oder relativen Pfad angeben.  **LINK** verwendet keine Umgebungsvariable für die Suche nach der Datei.  
  
 In der Befehlsdatei können die Argumente durch Leerzeichen oder Tabulatorzeichen \(wie in der Befehlszeile\), oder durch Zeilenumbruchzeichen voneinander getrennt werden.  
  
 Sie können die gesamte Befehlszeile oder nur einen Teil davon in einer Befehlsdatei angeben.  In einem **LINK**\-Befehl können mehrere Befehlsdateien verwendet werden.  **LINK** verarbeitet die Angaben in der Befehlsdatei genau so, wie die direkten Eingaben in der Befehlszeile.  Befehlsdateien können nicht geschachtelt werden.  **LINK** zeigt den Inhalt von Befehlsdateien am Bildschirm an, es sei denn, die Option [\/NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md) wird angegeben.  
  
## Beispiel  
 Der folgende Befehl zum Erstellen einer DLL übergibt die Namen von Objektdateien und Bibliotheken in separaten Befehlsdateien und verwendet eine dritte Befehlsdatei für die Angabe der Option \/EXPORTS:  
  
```  
link /dll @objlist.txt @liblist.txt @exports.txt  
```  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)