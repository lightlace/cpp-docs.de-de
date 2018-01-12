---
title: -SYMBOLE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /symbols
dev_langs: C++
helpviewer_keywords:
- symbols, dumping
- public symbols
- symbols, displaying COFF symbol table
- symbol tables
- SYMBOLS dumpbin option
- /SYMBOLS dumpbin option
- -SYMBOLS dumpbin option
ms.assetid: 34bcae90-4561-4c77-a80c-065508dec39a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fb8a1a42bf0bbb3b0bf9b907f93e1c9d0e69cf5b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="symbols"></a>/SYMBOLS
```  
/SYMBOLS  
```  
  
 Diese Option zeigt die COFF-Symboltabelle. Symboltabellen sind in allen Objektdateien vorhanden. Nur, wenn sie mit "/ Debug" verknüpft ist, wird in eine Bilddatei eine COFF-Symboltabelle angezeigt.  
  
 Im folgenden ist eine Beschreibung der Ausgabe für/Symbols. Weitere Informationen zur Bedeutung der/Symbols Ausgabe kann durch einen Blick in "Winnt.h" (IMAGE_SYMBOL und IMAGE_AUX_SYMBOL) oder in COFF-Dokumentation gefunden werden.  
  
 Betrachten Sie das folgende Beispiel Speicherabbild:  
  
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
  
## <a name="remarks"></a>Hinweise  
 Die folgende Beschreibung, die Zeilen, die mit einer Zahl Symbol beginnen beschreibt Spalten, die für Benutzer relevante Informationen an:  
  
-   Die erste dreistellige Zahl wird das Symbol Indexnummer.  
  
-   Wenn die dritte Spalte SECT enthält*x*, das Symbol ist in diesem Abschnitt der Objektdatei definiert. Aber wenn UNDEF angezeigt wird, ist nicht in diesem Objekt definiert und muss behoben werden, an anderer Stelle.  
  
-   Die fünfte Spalte (statisch und extern) informiert, ob das Symbol nur innerhalb dieses Objekt sichtbar ist, oder ob er öffentlich ist (sichtbar extern). Ein statisches Symbols _sym würde nicht mit einem öffentlichen Symboldateien _sym verknüpft werden; Diese würde zwei verschiedene Instanzen von Funktionen, die mit dem Namen _sym sein.  
  
 Die letzte Spalte in einer nummerierten Zeile wird den Symbolnamen, ergänzt sowohl undekorierten.  
  
 Nur die [/Headers](../../build/reference/headers.md) DUMPBIN-Option ist verfügbar für die Verwendung in den Dateien erstellt wird, mit der [/GL](../../build/reference/gl-whole-program-optimization.md) -Compileroption.  
  
## <a name="see-also"></a>Siehe auch  
 [DUMPBIN-Optionen](../../build/reference/dumpbin-options.md)