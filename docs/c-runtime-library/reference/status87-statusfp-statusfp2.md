---
title: _status87, _statusfp, _statusfp2 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _statusfp2
- _statusfp
- _status87
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
- _statusfp2
- _statusfp
- statusfp2
- _status87
- status87
- statusfp
dev_langs:
- C++
helpviewer_keywords:
- floating-point functions, getting status word
- floating-point numbers, status word
- status87 function
- status word, getting floating point
- statusfp function
- _statusfp function
- _statusfp2 function
- statusfp2 function
- _status87 function
- floating-point functions
- status word
ms.assetid: 7ef963fa-b1fb-429d-94d6-fbf282ab7432
caps.latest.revision: 20
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
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: a42b5d8811e108b727671921322423d186d73afd
ms.lasthandoff: 02/24/2017

---
# <a name="status87-statusfp-statusfp2"></a>_status87, _statusfp, _statusfp2
Ruft das Gleitkommastatuswort ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned int _status87( void );  
unsigned int _statusfp( void );  
void _statusfp2(unsigned int *px86, unsigned int *pSSE2)  
```  
  
#### <a name="parameters"></a>Parameter  
 `px86`  
 Diese Adresse ist mit dem Statuswort für die x87-Gleitkommaeinheit gefüllt.  
  
 `pSSE2`  
 Diese Adresse ist mit dem Statuswort für die SSE2-Gleitkommaeinheit gefüllt.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei `_status87` und `_statusfp` geben die Bits im zurückgegebenen den Gleitkommastatus an. Eine Definition zu den von `_statusfp` zurückgegebenen Bits enthält die FLOAT.H-Includedatei. Viele Funktionen der mathematischen Bibliothek ändern das Gleitkommastatuswort, was zu unvorhersehbaren Ergebnissen führt. Eine Optimierung kann Gleitkommaoperationen um die Aufrufe von `_status87`, `_statusfp` und verwandten Funktionen neu anordnen, kombinieren und vermeiden. Verwenden Sie die Compileroption [/Od (Deaktivieren (Debuggen))](../../build/reference/od-disable-debug.md) oder die Pragma-Direktive [fenv_access](../../preprocessor/fenv-access.md), um Optimierungen zu verhindern, durch die Gleitkommaoperationen neu angeordnet werden. Die Rückgabewerte von `_clearfp` und `_statusfp` sowie die Rückgabeparameter von `_statusfp2` sind zuverlässiger, wenn weniger Gleitkommaoperationen zwischen den bekannten Zuständen des Gleitkommastatusworts ausgeführt werden.  
  
## <a name="remarks"></a>Hinweise  
 Die `_statusfp`-Funktion ruft das Gleitkommastatuswort ab. Das Statuswort ist eine Kombination aus dem Gleitkommaprozessorstatus und anderen Bedingungen, die von dem Handler für Gleitkommaausnahmen – z. B. ein Gleitkomma-Stapelüberlauf und -Stapelunterlauf – erkannt werden. Ausnahmen ohne Maskierung werden überprüft, bevor der Inhalt des Statusworts zurückgegeben wird. Dies bedeutet, dass der Aufrufer über ausstehende Ausnahmen informiert wird. Auf x86-Plattformen gibt `_statusfp` eine Kombination von x87- und SSE2-Gleitkommastatus zurück. Auf x64-Plattformen basiert der zurückgegebene Status auf dem MXCSR-Status von SSE. Auf ARM-Plattformen gibt `_statusfp` den Status von dem FPSCR-Register zurück.  
  
 `_statusfp` ist eine plattformunabhängige, portable Version von `_status87`. Sie ist identisch mit `_status87` auf Intel (x86)-Plattformen und wird auch von den x64- und ARM-Plattformen unterstützt. Um sicherzustellen, dass Ihr Gleitkommacode für alle Architekturen portabel ist, verwenden Sie `_statusfp`. Wenn Ihre Zielobjekte nur x86-Plattformen sind, können Sie entweder `_status87` oder `_statusfp` verwenden.  
  
 Es empfiehlt sich eine Verwendung von `_statusfp2` für Chips (wie Pentium IV), die sowohl einen x87- als auch einen SSE2-Gleitkommaprozessor haben. Bei `_statusfp2` werden die Adressen ausgefüllt, indem sowohl für den x87- als auch SSE2-Gleitkommaprozessor das Gleitkommastatuswort verwendet wird. Bei einem Chip, der sowohl x87- als auch SSE2-Gleitkommaprozessoren unterstützt, wird EM_AMBIGUOUS auf 1 festgelegt, wenn `_statusfp` oder `_controlfp` verwendet wird und die Aktion mehrdeutig ist, da sie sich sowohl auf das x87- oder das SSE2-Gleitkommastatuswort beziehen kann. Die `_statusfp2`-Funktion wird nur auf x86-Plattformen unterstützt.  
  
 Diese Funktionen eignen sich nicht für [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) da die common Language Runtime (CLR) nur die standardmäßige gleitkommagenauigkeit unterstützt.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_status87`, `_statusfp`, `_statusfp2`|\<float.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_statusfp.c  
// Build by using: cl /W4 /Ox /nologo crt_statusfp.c  
// This program creates various floating-point errors and  
// then uses _statusfp to display messages that indicate these problems.  
  
#include <stdio.h>  
#include <float.h>  
#pragma fenv_access(on)  
  
double test( void )  
{  
   double a = 1e-40;  
   float b;  
   double c;  
  
   printf("Status = 0x%.8x - clear\n", _statusfp());  
  
   // Assignment into b is inexact & underflows:   
   b = (float)(a + 1e-40);  
   printf("Status = 0x%.8x - inexact, underflow\n", _statusfp());  
  
   // c is denormal:   
   c = b / 2.0;   
   printf("Status = 0x%.8x - inexact, underflow, denormal\n",   
            _statusfp());  
  
   // Clear floating point status:   
   _clearfp();  
   return c;  
}  
  
int main(void)  
{  
   return (int)test();  
}  
```  
  
```Output  
Status = 0x00000000 - clear  
Status = 0x00000003 - inexact, underflow  
Status = 0x00080003 - inexact, underflow, denormal  
```  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [_clear87, _clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)
