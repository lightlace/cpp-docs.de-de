---
title: _CrtSetReportHook2, _CrtSetReportHookW2
ms.date: 11/04/2016
api_name:
- _CrtSetReportHook2
- _CrtSetReportHookW2
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CrtSetReportHookW2
- CrtSetReportHook2
- _CrtSetReportHookW2
- _CrtSetReportHook2
helpviewer_keywords:
- CrtSetReportHook2 function
- _CrtSetReportHook2 function
- _CrtSetReportHookW2 function
- CrtSetReportHookW2 function
ms.assetid: 12e5f68d-c8a7-4b1a-9a75-72ba4a8592d0
ms.openlocfilehash: 37ec0cea3fb558a5926e6f9c707e0e5033a17222
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942215"
---
# <a name="_crtsetreporthook2-_crtsetreporthookw2"></a>_CrtSetReportHook2, _CrtSetReportHookW2

Installiert oder deinstalliert eine clientdefinierte Berichtsfunktion, indem sie mit dem Debug-Berichterstellungsprozess der C-Laufzeit verknüpft wird (nur Debugversion)

## <a name="syntax"></a>Syntax

```C
int _CrtSetReportHook2(
   int mode,
   _CRT_REPORT_HOOK pfnNewHook
);
int _CrtSetReportHookW2(
   int mode,
   _CRT_REPORT_HOOKW pfnNewHook
);
```

### <a name="parameters"></a>Parameter

*mode*<br/>
Die auszuführende Aktion: **_CRT_RPTHOOK_INSTALL** oder **_CRT_RPTHOOK_REMOVE**.

*pfnNewHook*<br/>
Berichtshook, der in der schmale oder breit Zeichen Version dieser Funktion installiert oder entfernt werden soll.

## <a name="return-value"></a>Rückgabewert

-1, wenn ein Fehler aufgetreten ist, bei dem **EINVAL** oder **ENOMEM** festgelegt wurde. Andernfalls wird der Verweis Zähler von *pfnnewhook* nach dem-Befehl zurückgegeben.

## <a name="remarks"></a>Hinweise

Mit **_CrtSetReportHook2** und **_CrtSetReportHookW2** können Sie eine Funktion hookor lösen, während mit [_CrtSetReportHook](crtsetreporthook.md) nur eine Funktion eingebunden werden kann.

**_CrtSetReportHook2** oder **_CrtSetReportHookW2** sollte anstelle von **_CrtSetReportHook** verwendet werden, wenn der Hook-Befehl in einer DLL erfolgt und mehrere DLLs geladen werden könnten und ihre eigenen Hook-Funktionen festlegen. In einem solchen Fall können DLLs in einer anderen Reihenfolge entladen werden als der, in der sie geladen wurden, und die Hookfunktion kann weiterhin auf eine entladene DLL zeigen. Alle Debugausgaben abstürzen den Prozess, wenn die Hook-Funktionen mit **_CrtSetReportHook**hinzugefügt wurden.

Alle mit **_CrtSetReportHook** hinzugefügten Hookfunktionen werden aufgerufen, wenn keine Hookfunktionen mit **_CrtSetReportHook2** oder **_CrtSetReportHookW2** hinzugefügt werden oder wenn alle mit **_CrtSetReportHook2** und _ hinzugefügten Hook-Funktionen vorhanden sind  **CrtSetReportHookW2** gibt **false**zurück.

Die Breitzeichenversion dieser Funktion ist verfügbar. Die Hookfunktionen für Berichte nehmen eine Zeichenfolge entgegen, deren Typ (breite oder schmale Zeichen) der Version der verwendeten Funktion entsprechen muss. Verwenden Sie den folgenden Prototyp einer Hookfunktion für Berichte in der Breitzeichenversion dieser Funktion:

```C
int YourReportHook( int reportType, wchar_t *message, int *returnValue );
```

Verwenden Sie den folgenden Prototyp der Hookfunktion für Berichte in der Schmalzeichenversion:

```C
int YourReportHook( int reportType, char *message, int *returnValue );
```

Diese Funktionen überprüfen ihre Parameter. Wenn *Mode* oder **pfnnewnook** ungültig ist, rufen diese Funktionen den Handler für ungültige Parameter auf, wie unter [Parameter Validierung](../../c-runtime-library/parameter-validation.md)beschrieben. Wenn die weitere Ausführung zugelassen wird, legen diese Funktionen **errno** auf **EINVAL** fest und geben-1 zurück.

> [!NOTE]
> Wenn die Anwendung mit **/CLR** kompiliert wird und die Berichterstattungs Funktion aufgerufen wird, nachdem die Anwendung beendet wurde, löst die CLR eine Ausnahme aus, wenn die Berichterstattungs Funktion eine CRT-Funktion aufruft.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_CrtSetReportHook2**|\<crtdbg.h>|\<errno.h>|
|**_CrtSetReportHookW2**|\<crtdbg.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
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

### <a name="output"></a>Ausgabe

```Output
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

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
