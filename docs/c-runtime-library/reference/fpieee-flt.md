---
title: _fpieee_flt | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: c2e9f909f3e7e778845d8fefebe5d8b1604af489
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="fpieeeflt"></a>_fpieee_flt
Ruft einen benutzerdefinierten Traphandler für IEEE-Gleitkommaausnahmen auf.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _fpieee_flt(   
   unsigned long excCode,  
   struct _EXCEPTION_POINTERS *excInfo,  
   int handler(_FPIEEE_RECORD *)   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `excCode`  
 Ausnahmecode.  
  
 `excInfo`  
 Zeiger zur Windows NT-Ausnahmeinformationsstruktur  
  
 `handler`  
 Zeiger zur IEEE-Traphandlerroutine des Benutzers.  
  
## <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert von `_fpieee_flt` ist der Wert, der von `handler` zurückgegeben wird. Daher wird die IEEE-Filterroutine möglicherweise in der except-Klausel eines strukturierten Ausnahmebehandlungsmechanismus (SEH) verwendet.  
  
## <a name="remarks"></a>Hinweise  
 Die `_fpieee_flt`-Funktion ruft einen benutzerdefinierten Traphandler für IEEE-Gleitkommaausnahmen auf und stellt ihn mit allen relevanten Informationen bereit. Diese Routine dient als Ausnahmefilter im SEH-Mechanismus, der bei Bedarf einen eigenen IEEE-Ausnahmehandler aufruft.  
  
 Die in Fpieee.h definierte `_FPIEEE_RECORD`-Struktur enthält Informationen zu einer IEEE-Gleitkommaausnahme. Diese Struktur wird von `_fpieee_flt` an den benutzerdefinierten Traphandler übergeben.  
  
|_FPIEEE_RECORD-Feld|Beschreibung|  
|----------------------------|-----------------|  
|`unsigned int RoundingMode`, `unsigned int Precision`|Diese Felder enthalten Informationen zur Gleitkommaumgebung zu dem Zeitpunkt, als die Ausnahme auftrat.|  
|`unsigned int Operation`|Gibt den Typ des Vorgangs an, der das Trap verursacht hat. Wenn der Typ ein Vergleich (`_FpCodeCompare`) ist, können Sie einen der speziellen `_FPIEEE_COMPARE_RESULT`-Werte (wie in Fpieee.h definiert) im `Result.Value`-Feld angeben. Der Konvertierungstyp (`_FpCodeConvert`) gibt an, dass das Trap während einer Gleitkommakonvertierung aufgetreten ist. Mithilfe der Typen `Operand1` und `Result` können Sie den Typ der versuchten Konvertierung bestimmen.|  
|`_FPIEEE_VALUE Operand1`, `_FPIEEE_VALUE Operand2`, `_FPIEEE_VALUE Result`|Diese Strukturen geben die Typen und Werte des vorgeschlagenen Ergebnisses und der Operanden an:<br /><br /> `OperandValid` Flag, das angibt, ob der Reaktionswert gültig ist.<br /><br /> `Format` Datentyp des entsprechenden Werts. Der Formattyp kann zurückgegeben werden, wenn der entsprechende Wert ungültig ist.<br /><br /> `Value` Ergebnis- oder Operandendatenwert|  
|`_FPIEEE_EXCEPTION_FLAGS Cause`, `_FPIEEE_EXCEPTION_FLAGS Enable`, `_FPIEEE_EXCEPTION_FLAGS Status`|_FPIEEE_EXCEPTION_FLAGS enthält ein Bitfeld pro Typ der Gleitkommaausnahme.<br /><br /> Es gibt eine Entsprechung zwischen diesen Feldern und den Argumenten, die verwendet werden, um die für [_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md) bereitgestellten Ausnahmen zu maskieren.<br /><br /> Die genaue Bedeutung der einzelnen Bits hängt vom Kontext ab:<br /><br /> `Cause` Jedes festgelegte Bit gibt die bestimmte Ausnahme an, die ausgelöst wurde.<br /><br /> `Enable` Jedes festgelegte Bit gibt an, dass die bestimmte Ausnahme zurzeit nicht maskiert ist.<br /><br /> `Status` Jedes festgelegte Bit gibt an, dass die bestimmte Ausnahme zurzeit aussteht. Dies schließt Ausnahmen ein, die nicht ausgelöst wurden, da sie von `_controlfp` maskiert wurden.|  
  
 Ausstehende, deaktivierte Ausnahmen werden bei Aktivierung ausgelöst. Dies kann zu einem nicht definierten Verhalten führen, wenn `_fpieee_flt` als Ausnahmefilter verwendet wird. Rufen Sie vor der Aktivierung von Gleitkommaausnahmen immer [_clearfp](../../c-runtime-library/reference/clear87-clearfp.md) auf.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`_fpieee_flt`|\<fpieee.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
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
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)   
 [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md)
