---
title: "Angeben einer Inlinedatei | Microsoft Docs"
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
  - "Dateien [C++], Inline"
  - "Inlinedateien [C++], Angeben von NMAKE"
  - "NMAKE (Programm), Inlinedateien"
ms.assetid: 393eccfb-3fc9-4bac-a30c-8ac8d221cca3
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Angeben einer Inlinedatei
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Geben Sie zwei spitze Klammern \(\<\<\) im Befehl an, in der *Dateiname*  angezeigt ist.  Von Winkelklammern kann keine Makroerweiterung dargestellt werden.  
  
## Syntax  
  
```  
<<[filename]  
```  
  
## Hinweise  
 Wenn der Befehl ausgeführt wird, werden die linken Winkelklammern durch *filename* \(falls angegeben\) oder durch einen eindeutigen Namen ersetzt, der von NMAKE generiert wird.  Falls angegeben, muss sich *filename* nach den linken Winkelklammern ohne ein Leerzeichen oder einen Tabstopp befinden.  Ein Pfad ist zulässig.  Eine Erweiterung ist nicht erforderlich oder wird nicht angenommen.  Wenn *filename* angegeben wird, wird die Datei in dem aktuellen oder angegebenen Verzeichnis erstellt, wobei eine vorhandene Datei mit diesem Namen ggf. überschrieben wird. Andernfalls wird sie in dem in der TMP\-Umgebungsvariablen angegebenen Verzeichnis oder dem aktuellen Verzeichnis, falls die TMP\-Umgebungsvariable nicht definiert ist, erstellt.  Wenn ein vorheriger *filename* wieder verwendet wird, wird die vorherige Datei von NMAKE ersetzt.  
  
## Siehe auch  
 [Inlinedateien in einem Makefile](../build/inline-files-in-a-makefile.md)