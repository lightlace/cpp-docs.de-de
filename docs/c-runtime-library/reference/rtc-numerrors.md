---
title: "_RTC_NumErrors"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_RTC_NumErrors"
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
  - "_RTC_NumErrors"
  - "RTC_NumErrors"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Laufzeitfehler"
  - "_RTC_NumErrors-Funktion"
  - "RTC_NumErrors-Funktion"
ms.assetid: 7e82adae-38e2-4f8b-bc0b-37bda8109fd1
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# _RTC_NumErrors
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt die Gesamtzahl der Fehler zurück, die durch die Fehlerprüfung zur Laufzeit \(RTC\) erkannt werden können. Sie können diese Zahl als Steuerung in einer **for**\-Schleife verwenden, wobei jeder Wert in der Schleife an [\_RTC\_GetErrDesc](../../c-runtime-library/reference/rtc-geterrdesc.md) übergeben wird.  
  
## Syntax  
  
```  
  
int _RTC_NumErrors( void );  
  
```  
  
## Rückgabewert  
 Eine ganze Zahl, deren Wert die Gesamtzahl der Fehler darstellt, die von den Visual C\+\+\-Fehlerprüfungen zur Laufzeit erkannt werden können.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_RTC_NumErrors`|\<rtcapi.h\>|  
  
 Weitere Informationen finden Sie unter[Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [\_RTC\_GetErrDesc](../../c-runtime-library/reference/rtc-geterrdesc.md)   
 [Laufzeitfehlerüberprüfung](../../c-runtime-library/run-time-error-checking.md)