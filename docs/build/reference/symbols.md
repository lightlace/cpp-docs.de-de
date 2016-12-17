---
title: "/SYMBOLS"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "/symbols"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SYMBOLS (dumpbin-Option)"
  - "Öffentliche Symbols"
  - "Symboltabellen"
  - "SYMBOLS (dumpbin-Option)"
  - "-SYMBOLS (dumpbin-Option)"
  - "Symbole, Anzeigen der COFF-Symboltabelle"
  - "Symbole, Dumperstellung"
ms.assetid: 34bcae90-4561-4c77-a80c-065508dec39a
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# /SYMBOLS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SYMBOLS  
```  
  
 Durch diese Option wird die COFF\-Symboltabelle angezeigt.  Symboltabellen gibt es in allen Objektdateien.  Eine COFF\-Symboltabelle wird nur in einer Bilddatei angezeigt, wenn sie mit **\/DEBUG** verknüpft ist.  
  
 Im Folgenden sehen Sie eine Beschreibung der **\/SYMBOLS**\-Ausgabe.  Zusätzliche Informationen zur Bedeutung der **\/SYMBOLS**\-Ausgabe finden Sie in **winnt.h** \(IMAGE\_SYMBOL und IMAGE\_AUX\_SYMBOL\) oder in der COFF\-Dokumentation.  
  
 Betrachten Sie das folgende Dumpbeispiel:  
  
```  
Dump of file main.obj  
File Type: COFF OBJECT  
  
COFF    SYMBOL    TABLE  
000    00000000   DEBUG      notype      Filename      | .file  
      main.cpp  
002   000B1FDB   ABS      notype      Static      | @comp.id  
003   00000000   SECT1      notype      Static      | .drectve  
      Section length       26, #relocs   0, #linenums    0, checksum 722C964F  
005   00000000   SECT2      notype      Static      | .text  
      Section length      23, #relocs      1, #linenums    0, checksum 459FF65F, selection    1 (pick no duplicates)  
007   00000000   SECT2      notype ()   External      | _main  
008   00000000   UNDEF      notype ()   External      | ?MyDump@@YAXXZ (void __cdecl MyDump(void))  
  
String Table Size = 0x10 bytes  
  
Summary  
  
      26 .drectve  
      23 .text  
```  
  
## Hinweise  
 In der folgenden Beschreibung werden bei Zeilen, die mit einer Symbolnummer beginnen, die Spalten mit wichtigen Informationen für den Benutzer erörtert:  
  
-   Die erste dreistellige Nummer entspricht dem Symbolindex bzw. der Symbolnummer.  
  
-   Enthält die dritte Spalte den Eintrag SECT*x*, ist das Symbol im betreffenden Abschnitt der Objektdatei definiert.  Wenn UNDEF angezeigt wird, ist es nicht in diesem Objekt definiert und muss anderweitig aufgelöst werden.  
  
-   Durch die fünfte Spalte \(Static, External\) wird angegeben, ob das Symbol nur in diesem Objekt sichtbar oder ob es öffentlich \(d. h. extern sichtbar\) ist.  Ein `Static`\-Symbol **\_sym** würde nicht mit einem `Public`\-Symbol **\_sym** verknüpft werden, da es sich um zwei verschiedene Funktionsinstanzen mit dem Namen "\_sym" handelt.  
  
 Die letzte Spalte in einer nummerierten Zeile entspricht dem Symbolnamen, der ergänzt oder nicht ergänzt sein kann.  
  
 Für Dateien, die mit der [\/GL](../../build/reference/gl-whole-program-optimization.md)\-Compileroption erstellt wurden, kann nur die DUMPBIN\-Option [\/HEADERS](../../build/reference/headers.md) verwendet werden.  
  
## Siehe auch  
 [DUMPBIN\-Optionen](../../build/reference/dumpbin-options.md)