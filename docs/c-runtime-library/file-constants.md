---
title: "Dateikonstanten"
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
  - "_O_EXCL"
  - "_O_RDWR"
  - "_O_APPEND"
  - "_O_RDONLY"
  - "_O_TRUNC"
  - "_O_CREAT"
  - "_O_WRONLY"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_O_APPEND-Konstante"
  - "_O_CREAT-Konstante"
  - "_O_EXCL-Konstante"
  - "_O_RDONLY-Konstante"
  - "_O_RDWR-Konstante"
  - "_O_TRUNC-Konstante"
  - "_O_WRONLY-Konstante"
  - "O_APPEND-Konstante"
  - "O_CREAT-Konstante"
  - "O_EXCL-Konstante"
  - "O_RDONLY-Konstante"
  - "O_RDWR-Konstante"
  - "O_TRUNC-Konstante"
  - "O_WRONLY-Konstante"
ms.assetid: c8fa5548-9ac2-4217-801d-eb45e86f2fa4
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Dateikonstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
#include <fcntl.h>  
  
```  
  
## Hinweise  
 Der ganzzahlige Ausdruck, der aus einer oder mehreren dieser Konstanten gebildet wird, bestimmt den Typ von den zulässigen Lese\- und Schreiboperationen.  Er wird gebildet, indem eine oder mehrere Konstanten mit einer ÜbersetzungModuskonstante kombiniert.  
  
 Die Dateikonstanten sind, wie folgt:  
  
 `_O_APPEND`  
 Ordnet der Dateizeiger am Ende der Datei vor den Schreibvorgang neu.  
  
 `_O_CREAT`  
 Erstellt und öffnet eine neue Datei zum Schreiben; dies hat keine Auswirkungen, wenn die Datei, die von *Dateinamen* angegeben wird, vorhanden ist.  
  
 `_O_EXCL`  
 Gibt einen Fehlerwert zurück, wenn die Datei, die von *Dateinamen* angegeben wird, vorhanden ist.  Gilt nur, wenn Sie mit `_O_CREAT` verwendet werden.  
  
 `_O_RDONLY`  
 Öffnet Datei nur für Lesezwecke; wenn dieses Flag, angegeben wird, können weder `_O_RDWR` noch `_O_WRONLY` angegeben werden.  
  
 `_O_RDWR`  
 Öffnet Datei für Lesen und Schreiben; wenn dieses Flag, angegeben wird, können weder `_O_RDONLY` noch `_O_WRONLY` angegeben werden.  
  
 `_O_TRUNC`  
 Öffnet und entfernt eine vorhandene Datei zur Länge 0 \(null\) ab; die Datei muss über eine Schreibberechtigung verfügen.  Der Inhalt der Datei wird gelöscht.  Wenn dieses Flag angegeben ist, können Sie `_O_RDONLY` nicht angeben.  
  
 `_O_WRONLY`  
 Öffnet Datei für nur geschrieben; wenn dieses Flag, angegeben wird, können weder `_O_RDONLY` noch `_O_RDWR` angegeben werden.  
  
## Siehe auch  
 [\_open, \_wopen](../c-runtime-library/reference/open-wopen.md)   
 [\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)