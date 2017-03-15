---
title: "Signalkonstanten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SIGTERM"
  - "SIGFPE"
  - "SIGABRT"
  - "SIGILL"
  - "SIGINT"
  - "SIGSEGV"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SIGABRT-Konstante"
  - "SIGFPE-Konstante"
  - "SIGILL-Konstante"
  - "SIGINT-Konstante"
  - "Signalkonstante"
  - "SIGSEGV-Konstante"
  - "SIGTERM-Konstante"
ms.assetid: a3b39281-dae7-4e44-8d68-e6a610c669dd
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Signalkonstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
#include <signal.h>  
```  
  
## Hinweise  
 Das `sig`\-Argument muss eine der Manifestkonstanten sein, unten aufgeführten \(definiert in SIGNAL.H\).  
  
 `SIGABRT`  
 Nicht ordnungsgemäß beendet.  Der Standardaktion beendet das aufrufende Programm mit Exitcode 3.  
  
 `SIGABRT_COMPAT`  
 Identisch mit SIGABRT.  Um Kompatibilität mit anderen Plattformen.  
  
 `SIGFPE`  
 Gleitkommafehler, wie Überlauf, Division durch 0 oder ungültiger Vorgang.  Der Standardaktion beendet das aufrufende Programm.  
  
 `SIGILL`  
 Nicht interpretierbarer Befehl.  Der Standardaktion beendet das aufrufende Programm.  
  
 `SIGINT`  
 STRG\+C\-Unterbrechung.  Der Standardaktion beendet das aufrufende Programm mit Exitcode 3.  
  
 `SIGSEGV`  
 Ungültiger Speicherzugriff.  Der Standardaktion beendet das aufrufende Programm.  
  
 `SIGTERM`  
 Abschlussanforderung gesendet dem Programm.  Der Standardaktion beendet das aufrufende Programm mit Exitcode 3.  
  
 `SIG_ERR`  
 Ein Rückgabetyp von einem Signal, das einen Fehler angibt, ist aufgetreten.  
  
## Siehe auch  
 [signal](../c-runtime-library/reference/signal.md)   
 [raise](../c-runtime-library/reference/raise.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)