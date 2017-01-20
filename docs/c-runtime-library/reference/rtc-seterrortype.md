---
title: "_RTC_SetErrorType"
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
  - "_RTC_SetErrorType"
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
  - "RTC_SetErrorType"
  - "_RTC_SetErrorType"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Laufzeitfehler"
  - "RTC_SetErrorType-Funktion"
  - "_RTC_SetErrorType-Funktion"
ms.assetid: f5f99be7-d357-4b11-b8f5-ddd3428f2b06
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# _RTC_SetErrorType
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ordnet einen Fehler, der von den Fehlerprüfungen zur Laufzeit \(RTCs\) erkannt wurde, einem Typ zu. Wie die Fehler des angegebenen Typs verarbeitet werden, hängt von Ihrem Fehlerhandler ab.  
  
## Syntax  
  
```  
  
int _RTC_SetErrorType(  
   _RTC_ErrorNumber  
errnum  
,  
   int  
ErrType   
);  
  
```  
  
#### Parameter  
 *errnum*  
 Eine Zahl zwischen null und einem um eins kleineren als dem von [\_RTC\_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md) zurückgegebenen Wert.  
  
 *ErrType*  
 Ein Wert, der dieser *errnum* zugewiesen werden soll. Sie können beispielsweise **\_CRT\_ERROR** verwenden. Wenn Sie `_CrtDbgReport` als Fehlerhandler verwenden, kann *ErrType* nur eins der in [\_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) definierten Symbole sein. Wenn Sie einen eigenen Fehlerhandler \([\_RTC\_SetErrorFunc](../../c-runtime-library/reference/rtc-seterrorfunc.md)\) verwenden, können Sie so viele *ErrType*s definieren, wie es *errnum*s gibt.  
  
 Ein *ErrType* von \_RTC\_ERRTYPE\_IGNORE hat für `_CrtSetReportMode` eine besondere Bedeutung; der Fehler wird ignoriert.  
  
## Rückgabewert  
 Der vorherige Wert für den Fehlertyp `type`.  
  
## Hinweise  
 Standardmäßig werden alle Fehler auf *ErrType* \= 1 festgelegt, was **\_CRT\_ERROR** entspricht. Weitere Informationen zu den Standardfehlertypen, wie etwa **\_CRT\_ERROR**, finden Sie unter [\_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md).  
  
 Bevor Sie diese Funktion aufrufen können, müssen Sie zuerst eine der Initialisierungsfunktionen der Laufzeitfehlerüberprüfung aufrufen; siehe dazu [Verwenden von Laufzeitüberprüfungen ohne die C\-Laufzeitbibliothek](../Topic/Using%20Run-Time%20Checks%20Without%20the%20C%20Run-Time%20Library.md)  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_RTC_SetErrorType`|\<rtcapi.h\>|  
  
 Weitere Informationen finden Sie unter[Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [\_RTC\_GetErrDesc](../../c-runtime-library/reference/rtc-geterrdesc.md)   
 [Laufzeitfehlerüberprüfung](../../c-runtime-library/run-time-error-checking.md)