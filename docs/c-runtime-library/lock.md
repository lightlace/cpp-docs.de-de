---
title: "_lock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_lock"
apilocation: 
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcrt.dll"
  - "msvcr120_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "lock"
  - "_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lock-Funktion"
  - "_lock-Funktion"
ms.assetid: 29f77c37-30de-4b3d-91b6-030216e645a6
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# _lock
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft eine Multi\-Thread\-Sperre ab.  
  
> [!IMPORTANT]
>  Diese Funktion ist veraltet. Von Visual Studio 2015 an ist sie nicht in der CRT verfügbar.  
  
## Syntax  
  
```  
void __cdecl _lock  
   int locknum  
);  
```  
  
#### Parameter  
 \[in\] `locknum`  
 Der Bezeichner der abzurufenden Sperre.  
  
## Hinweise  
 Wenn die Sperre bereits abgerufen wurde, ruft diese Methode die Sperre dennoch ab und verursacht einen internen C\-Laufzeitfehler \(CRT\). Wenn die Methode keine Sperre abrufen kann, wird sie mit einem schwerwiegenden Fehler beendet und der Fehlercode auf `_RT_LOCK` festgelegt.  
  
## Anforderungen  
 **Quelle:** mlock.c  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [\_unlock](../c-runtime-library/unlock.md)