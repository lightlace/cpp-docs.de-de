---
title: "_purecall | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_purecall"
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
  - "ntoskrnl.exe"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "purecall"
  - "_purecall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_purecall-Funktion"
  - "purecall-Funktion"
ms.assetid: 56135d9b-3403-4e22-822d-e714523801cc
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# _purecall
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der standardmäßige rein virtuelle Funktion Aufruf Fehler\-Handler. Der Compiler generiert Code zum Aufrufen dieser Funktion, wenn eine rein virtuelle Memberfunktion aufgerufen wird.  
  
## Syntax  
  
```  
extern "C" int __cdecl _purecall();  
```  
  
## Hinweise  
 Die `_purecall` \-Funktion ist eine Microsoft\-spezifische Implementierungsdetail des Microsoft Visual C\+\+\-Compilers. Diese Funktion ist nicht vorgesehen, direkt vom Code aufgerufen werden, und es wurde keine öffentlichen Header\-Deklaration. Es ist hier dokumentiert, da es sich um eine öffentliche Exportieren von C\-Laufzeitbibliothek ist.  
  
 Ein Aufruf einer rein virtuelle Funktion ist ein Fehler auf, da sie keine Implementierung hat. Der Compiler generiert Code zum Aufrufen der `_purecall` Fehler\-Handler\-Funktion, wenn eine reine virtuelle Funktion aufgerufen wird. In der Standardeinstellung `_purecall` wird das Programm beendet. Vor dem Beenden, die `_purecall` \-Funktion aufruft, eine `_purecall_handler` ausgeführt werden, wenn eine für den Prozess festgelegt wurde. Sie können Ihre eigenen fehlerhandlerfunktion für rein virtuelle Funktionsaufrufen, um sie für das Debuggen und Berichtszwecke abfangen installieren. Um Ihre eigenen Fehler\-Handler zu verwenden, erstellen Sie eine Funktion mit der `_purecall_handler` Signatur verwenden [\_set\_purecall\_handler](../../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md) den aktuellen Handler machen.  
  
## Anforderungen  
 Die `_purecall` \-Funktion verfügt über eine Header\-Deklaration. Die `_purecall_handler` Typedef in \< stdlib.h \> definiert ist.  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [\_get\_purecall\_handler \_set\_purecall\_handler](../../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)