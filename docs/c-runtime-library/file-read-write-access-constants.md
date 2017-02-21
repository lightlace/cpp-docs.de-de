---
title: "Datei-Lese-/Schreibzugriffkonstanten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.constants.file"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zugriffkonstanten für Datei-Lese-/Schreibvorgänge"
  - "Konstanten [C++], Dateiattribute"
  - "Datei-Lese-/Schreibzugriffkonstanten"
  - "Lese- und Schreibzugriffkonstanten"
  - "Schreibzugriffkonstanten"
ms.assetid: 56cd1d22-39a5-4fcf-bea2-7046d249e8ee
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Datei-Lese-/Schreibzugriffkonstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
#include <stdio.h>  
```  
  
## Hinweise  
 Diese Konstanten geben den Zugriffstyp \("a", "r", oder "w"\) angefordert für die Datei an.  können das [Übersetzungsmodus](../c-runtime-library/file-translation-constants.md) \("b" oder "t"\) und die [Datenträgercommitmodus](../c-runtime-library/commit-to-disk-constants.md) \("c" oder "n"\) mit dem Typ des Zugriffs angegeben werden.  
  
 Die Zugriffstypen werden nachstehend beschrieben.  
  
 **"a"**  
 Öffnet sich zum Schreiben am Ende der Datei \(Anfügen\); erstellt die Datei zuerst, wenn es nicht vorhanden ist.  Alle Schreibvorgänge treten am Ende der Datei auf.  Obwohl der Dateizeiger mithilfe von `fseek` bzw. **rewind** neu angeordnet werden kann, wird er immer wieder am Ende der Datei verschoben, bevor ein Schreibvorgang durchgeführt wird.  
  
 **"a\+"**  
 Wie wie oben, aber ermöglicht auch Lesen.  
  
 **"r"**  
 Öffnet zum Lesen.  Wenn die Datei nicht gefunden ist nicht vorhanden oder kann, schlägt der Aufruf, um die Datei zu öffnen aus.  
  
 **"r\+"**  
 Öffnet sowohl zum Lesen als auch zum Schreiben.  Wenn die Datei nicht gefunden ist nicht vorhanden oder kann, schlägt der Aufruf, um die Datei zu öffnen aus.  
  
 **"w"**  
 Öffnet eine leere Datei zum Schreiben.  Wenn die angegebene Datei vorhanden ist, wird ihr Inhalt zerstört.  
  
 **"w\+"**  
 Öffnet eine leere Datei zum Lesen und Schreiben.  Wenn die angegebene Datei vorhanden ist, wird ihr Inhalt zerstört.  
  
 Wenn der "R\+", "w\+" oder "a\+\-" Typ, angegeben wird, wird das Lesen und Schreiben zulässt \(die Datei soll für "Update" geöffnet\).  Wenn Sie zwischen das Lesen und Schreiben wechseln, es dazwischenliegendes `fflush`, `fsetpos`, `fseek` oder **rewind** geben Vorgang müssen.  Die aktuelle Position kann für den `fsetpos` oder `fseek` Vorgang angegeben werden.  
  
## Siehe auch  
 [\_fdopen, \_wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fopen, \_wfopen](../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, \_wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)   
 [\_fsopen, \_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [\_popen, \_wpopen](../c-runtime-library/reference/popen-wpopen.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)