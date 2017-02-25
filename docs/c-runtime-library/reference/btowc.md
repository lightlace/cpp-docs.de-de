---
title: "btowc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "btowc"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "btowc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "btowc-Funktion"
ms.assetid: 99a46e02-6f86-4569-af79-5feca012add8
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# btowc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmen, ob eine ganze Zahl ein gültiges Einzelbytezeichen im ursprünglichen Schichtzustand darstellt.  
  
## Syntax  
  
```  
wint_t btowc(  
   int c  
);  
```  
  
#### Parameter  
 `c`  
 Zu testende ganze Zahl.  
  
## Rückgabewert  
 Gibt die Breitzeichendarstellung des Zeichens zurück, wenn die ganze Zahl ein gültiges Einzelbytezeichen im ursprünglichen Schichtzustand darstellt.  Gibt WEOF zurück, wenn die ganze Zahl EOF ist oder kein gültiges Einzelbytezeichen im ursprünglichen Schichtzustand ist.  Die Ausgabe dieser Funktion wird durch das aktuelle `LC_TYPE` Gebietsschema beeinflusst.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`btowc`|\<stdio.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [mbtowc, \_mbtowc\_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)