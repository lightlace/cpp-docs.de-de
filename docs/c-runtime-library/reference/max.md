---
title: "__max | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__max"
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
  - "max"
  - "__max"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__max-Makro"
  - "max-Makro"
  - "maximum-Makro"
ms.assetid: 05c936f6-0e22-45d6-a58d-4bc102e9dae2
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# __max
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt den größeren Ausdruck von zwei Werte zurück.  
  
## Syntax  
  
```  
type __max(  
   type a,  
   type b   
);  
```  
  
#### Parameter  
 `type`  
 Ein beliebiger numerischer Datentyp.  
  
 `a, b`  
 Werte eines zu vergleichenden numerischen Typs.  
  
## Rückgabewert  
 `__max` gibt das größere der Argumente zurück.  
  
## Hinweise  
 Das Makro `__max` vergleicht zwei Werte und gibt den Wert der größeren zurück.  Die Argumente können von einem beliebigen numerischen Datentyp sein, mit oder ohne Vorzeichen.  müssen Argumente und der Rückgabewert dem gleichen Datentyp.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`__max`|\<stdlib.h\>|  
  
## Beispiel  
 Weitere Informationen finden Sie im Beispiel für [\_\_min](../../c-runtime-library/reference/min.md).  
  
## .NET Framework-Entsprechung  
 [System::Math::Max](https://msdn.microsoft.com/en-us/library/system.math.max.aspx)  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [\_\_min](../../c-runtime-library/reference/min.md)