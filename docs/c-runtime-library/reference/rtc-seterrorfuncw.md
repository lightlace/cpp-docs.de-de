---
title: "_RTC_SetErrorFuncW"
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
  - "_RTC_SetErrorFuncW"
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
  - "_RTC_SetErrorFuncW"
  - "RTC_SetErrorFuncW"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Laufzeitfehler"
  - "RTC_SetErrorFuncW-Funktion"
  - "_RTC_error_fnW-Typedef"
  - "_RTC_SetErrorFuncW-Funktion"
  - "RTC_error_fnW-Typedef"
ms.assetid: b3e0d71f-1bd3-4c37-9ede-2f638eb3c81a
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# _RTC_SetErrorFuncW
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt eine Funktion als den Handler für das Melden von Fehlern der Fehlerprüfung zur Laufzeit \(RTCs\) fest.  
  
## Syntax  
  
```  
  
_RTC_error_fnW _RTC_SetErrorFuncW(  
   _RTC_error_fnW  
 function   
);  
  
```  
  
#### Parameter  
 `function`  
 Die Adresse der Funktion, die Fehlerprüfungen zur Laufzeit verarbeitet.  
  
## Rückgabewert  
 Die zuvor definierte Fehlerfunktion oder `NULL`, wenn keine zuvor definierte Funktion vorhanden ist.  
  
## Hinweise  
 Verwenden Sie in neuem Code ausschließlich `_RTC_SetErrorFuncW`.`_RTC_SetErrorFunc` ist in der Bibliothek nur noch aus Gründen der Abwärtskompatibilität enthalten.  
  
 Der Rückruf `_RTC_SetErrorFuncW` gilt nur für die Komponente, für die er eingebunden wurde, aber nicht global.  
  
 Stellen Sie sicher, dass die Adresse, die Sie an `_RTC_SetErrorFuncW` übergeben, zu einer gültigen Fehlerbehandlungsfunktion gehört.  
  
 Wenn einem Fehler durch [\_RTC\_SetErrorType](../../c-runtime-library/reference/rtc-seterrortype.md) der Typ „\-1“ zugewiesen wurde, wird die Fehlerbehandlungsfunktion nicht aufgerufen.  
  
 Bevor Sie diese Funktion aufrufen können, müssen Sie zuerst eine der Initialisierungsfunktionen der Laufzeitfehlerüberprüfung aufrufen. Weitere Informationen finden Sie unter [Verwenden von Laufzeitüberprüfungen ohne die C\-Laufzeitbibliothek](../Topic/Using%20Run-Time%20Checks%20Without%20the%20C%20Run-Time%20Library.md).  
  
 **\_RTC\_error\_fnW** ist wie folgt definiert:  
  
 **typedef int \(\_\_cdecl \*\_RTC\_error\_fnW\)\(int**  `errorType` **, const wchar\_t \*** *filename* **, int**  *linenumber* **, const wchar\_t \*** `moduleName` **, const wchar\_t \*** *format* **, ...\);**  
  
 Dabei gilt:  
  
 `errorType`  
 Die Art des Fehlers, der von [\_RTC\_SetErrorType](../../c-runtime-library/reference/rtc-seterrortype.md) angegeben wird.  
  
 *filename*  
 Die Quelldatei, in der der Fehler aufgetreten ist oder null, wenn keine Debuginformationen verfügbar sind.  
  
 *linenumber*  
 Die Zeile in *filename*, in der der Fehler aufgetreten ist oder „0“, wenn keine Debuginformationen verfügbar sind.  
  
 `moduleName`  
 Die DLL oder Name des ausführbaren Programms, wo der Fehler aufgetreten ist.  
  
 *format*  
 printf\-Formatzeichenfolge, um eine Fehlermeldung mit den übrigen Parameter anzuzeigen. Das erste Argument von VA\_ARGLIST ist die Fehlernummer des aufgetretenen RTC\-Fehlers.  
  
 Ein Beispiel für die Verwendung von **\_RTC\_error\_fnW** finden Sie unter [Anpassen der systemeigenen Laufzeitüberprüfung](../Topic/Native%20Run-Time%20Checks%20Customization.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_RTC_SetErrorFuncW`|\<rtcapi.h\>|  
  
 Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [\_CrtDbgReport, \_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)   
 [Laufzeitfehlerüberprüfung](../../c-runtime-library/run-time-error-checking.md)