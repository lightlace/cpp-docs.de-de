---
title: "_CrtSetReportHook2, _CrtSetReportHookW2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetReportHook2"
  - "_CrtSetReportHookW2"
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
  - "CrtSetReportHookW2"
  - "CrtSetReportHook2"
  - "_CrtSetReportHookW2"
  - "_CrtSetReportHook2"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CrtSetReportHook2-Funktion"
  - "_CrtSetReportHook2-Funktion"
  - "_CrtSetReportHookW2-Funktion"
  - "CrtSetReportHookW2-Funktion"
ms.assetid: 12e5f68d-c8a7-4b1a-9a75-72ba4a8592d0
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _CrtSetReportHook2, _CrtSetReportHookW2
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Installiert oder deinstalliert eine clientdefinierte Berichtsfunktion, indem sie das Verbinden der C\-Laufzeit, debuggen Berichterstellungsprozess Debugversion \(nur\).  
  
## Syntax  
  
```  
  
      int _CrtSetReportHook2(  
   int mode,  
   _CRT_REPORT_HOOK pfnNewHook  
);  
int _CrtSetReportHookW2(  
   int mode,  
   _CRT_REPORT_HOOKW pfnNewHook  
);  
```  
  
#### Parameter  
 `mode`  
 Die Aktion zu entladen: `_CRT_RPTHOOK_INSTALL` oder `_CRT_RPTHOOK_REMOVE`.  
  
 `pfnNewHook`  
 Beschreiben Sie über Hook, um in der EngeZeichenversion dieser Funktion zu installieren oder entfernen.  
  
 `pfnNewHook`  
 Beschreiben Sie über Hook, um in der Breitzeichen\-Version dieser Funktion zu installieren oder entfernen.  
  
## Rückgabewert  
 \-1, wenn ein Fehler aufgetreten ist, mit `EINVAL` oder `ENOMEM` legen Sie fest; gibt andernfalls den Verweiszähler von `pfnNewHook` nach dem Aufruf zurück.  
  
## Hinweise  
 `_CrtSetReportHook2` und `_CrtSetReportHookW2`  können Sie eine Funktion einzubinden bzw. die Verknüpfung [\_CrtSetReportHook](../../c-runtime-library/reference/crtsetreporthook.md) aufheben, während Sie nur eine Funktion verknüpfen können.  
  
 `_CrtSetReportHook2` oder `_CrtSetReportHookW2`  anstelle `_CrtSetReportHook` verwendet werden, wenn der Hookaufruf erfolgt in einer DLL festzulegen, können und als mehrere DLLs geladen werden und ihre eigenen Hookfunktionen.  In einer solchen Situation können DLLs in einer Reihenfolge, als entladen werden sie geladen wurden und die Hookfunktion an einer, entladenen DLL sich zu veranschaulichen verbleiben kann.  Alle debuggen Ausgabeabstürze der Prozess, wenn die Hookfunktionen mit `_CrtSetReportHook` hinzugefügt wurden.  
  
 Alle Hookfunktionen, die mit `_CrtSetReportHook` hinzugefügt, werden aufgerufen, wenn es keine Hookfunktionen gibt, die mit `_CrtSetReportHook2` hinzugefügt oder `_CrtSetReportHookW2` , oder wenn alle Hookfunktionen, die mit `_CrtSetReportHook2` und `_CrtSetReportHookW2`  hinzugefügt werden, `FALSE` zurückgeben.  
  
 Die Breitzeichen\-Version dieser Funktion ist verfügbar.  Die Hookfunktionen für Berichte erstellen eine Zeichenfolge, deren Typ \(weit schmale oder Zeichen\) die Version dieser verwendete Funktion übereinstimmen muss.  Verwenden Sie folgenden Funktionsprototyp für die Berichtshooks, die mit der Breitzeichen\-Version dieser Funktion verwendet werden:  
  
```  
int YourReportHook( int reportType, wchar_t *message, int *returnValue );  
```  
  
 Verwenden Sie folgenden Prototyp für die EngeZeichenberichtshooks:  
  
```  
int YourReportHook( int reportType, char *message, int *returnValue );  
```  
  
 Diese Funktionen überprüfen ihre Parameter.  Wenn `mode` oder `pfnNewNook` ungültig ist, rufen diese Funktionen den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben – 1 zurück.  
  
> [!NOTE]
>  Wenn die Anwendung mit `/clr` kompiliert und die Berichtsfunktion nach dem Beenden der Anwendung "Main" aufgerufen wird, löst die CLR eine Ausnahme aus, wenn die Berichterstellungsfunktion eine CRT\-Funktion aufruft.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_CrtSetReportHook2`|\<crtdbg.h\>|\<errno.h\>|  
|`_CrtSetReportHookW2`|\<crtdbg.h\>|\<errno.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Nur Debugversionen von [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_setreporthook2.c  
#include <windows.h>  
#include <stdio.h>  
#include <crtdbg.h>  
#include <assert.h>  
  
int __cdecl TestHook1(int nReportType, char* szMsg, int* pnRet)  
{  
   int nRet = FALSE;  
  
   printf("CRT report hook 1.\n");  
   printf("CRT report type is \"");  
   switch (nReportType)  
   {  
      case _CRT_ASSERT:  
      {  
         printf("_CRT_ASSERT");  
         // nRet = TRUE;   // Always stop for this type of report  
         break;  
      }  
  
      case _CRT_WARN:  
      {  
         printf("_CRT_WARN");  
         break;  
      }  
  
      case _CRT_ERROR:  
      {  
         printf("_CRT_ERROR");  
         break;  
      }  
  
      default:  
      {  
         printf("???Unknown???");  
         break;  
      }  
   }  
  
   printf("\".\nCRT report message is:\n\t");  
   printf(szMsg);  
  
   if   (pnRet)  
      *pnRet = 0;  
  
   return   nRet;  
}  
  
int __cdecl   TestHook2(int nReportType, char* szMsg, int* pnRet)  
{  
   int   nRet = FALSE;  
  
   printf("CRT report hook 2.\n");  
   printf("CRT report type is \"");  
   switch   (nReportType)  
   {  
      case _CRT_WARN:  
      {  
         printf("_CRT_WARN");  
         break;  
      }  
  
      case _CRT_ERROR:  
      {  
         printf("_CRT_ERROR");  
         break;  
      }  
  
      case _CRT_ASSERT:  
      {  
         printf("_CRT_ASSERT");  
         nRet = TRUE;   // Always stop for this type of report  
         break;  
      }  
  
      default:  
      {  
         printf("???Unknown???");  
         break;  
      }  
   }  
  
   printf("\".\nCRT report message is: \t");  
   printf(szMsg);  
  
   if   (pnRet)  
      *pnRet = 0;  
   // printf("CRT report code is %d.\n", *pnRet);  
   return   nRet;  
}  
  
int   main(int argc, char* argv[])  
{  
   int   nRet = 0;  
  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1)"  
          " returned %d\n", nRet);  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2)"  
          " returned %d\n", nRet);  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2)"  
          " returned %d\n", nRet);  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1)"  
          " returned %d\n", nRet);  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1)"  
          " returned %d\n", nRet);  
  
   _ASSERT(0);  
  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2)"  
          " returned %d\n", nRet);  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2)"  
          " returned %d\n", nRet);  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2)"  
          " returned %d\n", nRet);  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1)"  
          " returned %d\n", nRet);  
  
   return   nRet;  
}  
```  
  
## Ausgabe  
  
```  
_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1) returned 0  
```  
  
## Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)