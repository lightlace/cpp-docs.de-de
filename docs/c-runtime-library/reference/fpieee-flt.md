---
title: _fpieee_flt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _fpieee_flt
apilocation:
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fpieee_flt
- _fpieee_flt
dev_langs:
- C++
helpviewer_keywords:
- _fpieee_flt function
- exception handling, floating-point
- floating-point exception handling
- fpieee_flt function
ms.assetid: 2bc4801e-0eed-4e73-b518-215da8cc9740
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 412eef6e3999c18901792643fa7a57ce18d19520
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="fpieeeflt"></a>_fpieee_flt

Ruft einen benutzerdefinierten Traphandler für IEEE-Gleitkommaausnahmen auf.

## <a name="syntax"></a>Syntax

```C
int _fpieee_flt(
   unsigned long excCode,
   struct _EXCEPTION_POINTERS *excInfo,
   int handler(_FPIEEE_RECORD *)
);
```

### <a name="parameters"></a>Parameter

*excCode*<br/>
Ausnahmecode.

*excInfo*<br/>
Zeiger zur Windows NT-Ausnahmeinformationsstruktur

*Ereignishandler*<br/>
Zeiger zur IEEE-Traphandlerroutine des Benutzers.

## <a name="return-value"></a>Rückgabewert

Der Rückgabewert der **_fpieee_flt** ist der zurückgegebene Wert *Handler*. Daher wird die IEEE-Filterroutine möglicherweise in der except-Klausel eines strukturierten Ausnahmebehandlungsmechanismus (SEH) verwendet.

## <a name="remarks"></a>Hinweise

Die **_fpieee_flt** Funktion ruft einen benutzerdefinierten traphandler für IEEE-Gleitkommaausnahmen und mit allen relevanten Informationen bereitgestellt. Diese Routine dient als Ausnahmefilter im SEH-Mechanismus, der bei Bedarf einen eigenen IEEE-Ausnahmehandler aufruft.

Die **_FPIEEE_RECORD** in Fpieee.h definierte Struktur enthält Informationen zu einer IEEE-Gleitkommaausnahme. Diese Struktur wird übergeben, um den benutzerdefinierten traphandler durch **_fpieee_flt**.

|_FPIEEE_RECORD-Feld|Beschreibung|
|----------------------------|-----------------|
|**RoundingMode**<br/>**Genauigkeit**|Diese **ohne Vorzeichen** **Int** Felder enthalten Informationen zur gleitkommaumgebung zu dem Zeitpunkt der Ausnahme.|
|**Vorgang**|Dies **ohne Vorzeichen** **Int** Feld gibt den Typ des Vorgangs, der das Trap verursacht hat. Wenn der Typ einen Vergleich (**_FpCodeCompare**), geben Sie einen der speziellen **_FPIEEE_COMPARE_RESULT** Werte (wie in Fpieee.h definiert) in der **Result.Value** Feld. Der Konvertierungstyp (**_FpCodeConvert**) gibt an, dass das Trap während einer gleitkommakonvertierung aufgetreten sind. Sie können sehen Sie sich die **Operand1** und **Ergebnis** Typen, die den Typ der versuchten Konvertierung zu bestimmen.|
|**Operand1**<br/>**operand2**<br/>**Ergebnis**|Diese **_FPIEEE_VALUE** Strukturen geben die Typen und Werte des vorgeschlagenen Ergebnisses und der Operanden. Jede Struktur enthält folgende Felder:<br /><br /> **OperandValid** - Flag, das angibt, ob der reaktionswert gültig ist.<br />**Format** -Datentyp des entsprechenden Werts. Der Formattyp kann zurückgegeben werden, wenn der entsprechende Wert ungültig ist.<br />**Wert** -Ergebnis oder operandendatenwert.|
|**Ursache**<br/>**Aktivieren**<br/>**Status**|**_FPIEEE_EXCEPTION_FLAGS** enthält ein Bitfeld pro Typ von floating Point-Ausnahme. Es gibt eine Entsprechung zwischen diesen Feldern und den Argumenten, die verwendet werden, um die für [_controlfp](control87-controlfp-control87-2.md) bereitgestellten Ausnahmen zu maskieren. Die genaue Bedeutung der einzelnen Bits hängt vom Kontext ab:<br /><br /> **Ursache** -jedes festgelegte Bit gibt an, die bestimmte Ausnahme, die ausgelöst wurde.<br />**Aktivieren Sie** -jedes festgelegte Bit gibt an, dass die bestimmte Ausnahme zurzeit nicht maskiert ist.<br />**Status** -jedes festgelegte Bit gibt an, dass die bestimmte Ausnahme zurzeit aussteht. Dies schließt Ausnahmen, die nicht ausgelöst wurden, da sie von maskiert wurden **_controlfp**.|

Ausstehende, deaktivierte Ausnahmen werden bei Aktivierung ausgelöst. Dies kann zu nicht definiertem Verhalten bei Verwendung **_fpieee_flt** als Ausnahmefilter. Rufen Sie vor der Aktivierung von Gleitkommaausnahmen immer [_clearfp](clear87-clearfp.md) auf.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**_fpieee_flt**|\<fpieee.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_fpieee.c
// This program demonstrates the implementation of
// a user-defined floating-point exception handler using the
// _fpieee_flt function.

#include <fpieee.h>
#include <excpt.h>
#include <float.h>
#include <stddef.h>

int fpieee_handler( _FPIEEE_RECORD * );

int fpieee_handler( _FPIEEE_RECORD *pieee )
{
   // user-defined ieee trap handler routine:
   // there is one handler for all
   // IEEE exceptions

   // Assume the user wants all invalid
   // operations to return 0.

   if ((pieee->Cause.InvalidOperation) &&
       (pieee->Result.Format == _FpFormatFp32))
   {
        pieee->Result.Value.Fp32Value = 0.0F;

        return EXCEPTION_CONTINUE_EXECUTION;
   }
   else
      return EXCEPTION_EXECUTE_HANDLER;
}

#define _EXC_MASK    \
    _EM_UNDERFLOW  + \
    _EM_OVERFLOW   + \
    _EM_ZERODIVIDE + \
    _EM_INEXACT

int main( void )
{
   // ...

   __try {
      // unmask invalid operation exception
      _controlfp_s(NULL, _EXC_MASK, _MCW_EM);

      // code that may generate
      // fp exceptions goes here
   }
   __except ( _fpieee_flt( GetExceptionCode(),
                GetExceptionInformation(),
                fpieee_handler ) ){

      // code that gets control

      // if fpieee_handler returns
      // EXCEPTION_EXECUTE_HANDLER goes here

   }

   // ...
}
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md)<br/>
[_controlfp_s](controlfp-s.md)<br/>
