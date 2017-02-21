---
title: "_get_printf_count_output | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_printf_count_output"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "get_printf_count_output"
  - "_get_printf_count_output"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "%n-Format"
  - "_get_printf_count_output-Funktion"
  - "get_printf_count_output-Funktion"
ms.assetid: 850f9f33-8319-433e-98d8-6a694200d994
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _get_printf_count_output
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt dass [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)\- Familienfunktionen unterstützen das Format `%n`.  
  
## Syntax  
  
```  
int _get_printf_count_output();  
```  
  
## Rückgabewert  
 Wert ungleich 0 \(null\), wenn `%n` unterstützt wird, 0, wenn `%n` nicht unterstützt wird.  
  
## Hinweise  
 Wenn `%n` \(Standard\) nicht unterstützt wird, `%n` in der Formatzeichenfolge eine der Funktionen `printf` antreffend ruft den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn `%n` Unterstützung aktiviert ist \(siehe [\_set\_printf\_count\_output](../../c-runtime-library/reference/set-printf-count-output.md)\), dass selbst dann `%n` verhält, wie in [printf\-Typenfeldzeichen](../../c-runtime-library/printf-type-field-characters.md) beschrieben.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_get_printf_count_output`|\<stdio.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Ein Beispiel hierfür finden Sie unter [\_set\_printf\_count\_output](../../c-runtime-library/reference/set-printf-count-output.md).  
  
## Entsprechung in .NET Framework  
 Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).