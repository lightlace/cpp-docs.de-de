---
title: "_amsg_exit"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_amsg_exit"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_amsg_exit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_amsg_exit"
ms.assetid: 146d4faf-d763-43a4-b264-12711196456b
caps.latest.revision: 2
caps.handback.revision: "2"
ms.author: "corob"
manager: "ghogen"
---
# _amsg_exit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt eine angegebene Ablauffehlermeldung aus und beendet die Anwendung anschließend mit Fehlercode 255.  
  
## Syntax  
  
```cpp  
void _amsg_exit (  
   int rterrnum  
   )  
  
```  
  
#### Parameter  
 `rterrnum`  
 Die ID einer Kategorie Ablauffehlermeldung.  
  
## Hinweise  
 Diese Funktion gibt die Ablauffehlermeldung an **stderr** für Konsolenanwendungen ab oder zeigt die Meldung in einem Meldungsfeld für Windows\-Anwendungen an.  Im Debugmodus können Sie auswählen, um den Debugger aufzurufen, bevor Sie beenden.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|\_amsg\_exit|internal.h|