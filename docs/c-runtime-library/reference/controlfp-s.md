---
title: _controlfp_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _controlfp_s
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
- controlfp_s
- _controlfp_s
dev_langs:
- C++
helpviewer_keywords:
- floating-point numbers, control word
- controlfp_s function
- floating-point functions, setting control word
- EM_AMBIGUOUS
- _controlfp_s function
ms.assetid: a51fc3f6-ab13-41f0-b227-6bf02d98e987
caps.latest.revision: 28
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 1a00023e4d3e31ddb6381e90a50231449b1de18d
ms.openlocfilehash: 4345539f7ecd836280bed94c4bb2b125dfa08107
ms.contentlocale: de-de
ms.lasthandoff: 02/28/2017

---
# <a name="controlfps"></a>_controlfp_s
Ruft das Gleitkommasteuerwort ab und legt es fest. Diese Version von [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) enthält Sicherheitsverbesserungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t _controlfp_s(  
    unsigned int *currentControl,  
    unsigned int newControl,  
    unsigned int mask  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `currentControl`  
 Der aktuelle Bitwert des Steuerworts.  
  
 `newControl`  
 Neue Bitwerte des Steuerworts.  
  
 `mask`  
 Maske für festzulegende neue Steuerwortbits.  
  
## <a name="return-value"></a>Rückgabewert  
 Null, wenn erfolgreich, oder ein Fehlercode des Wertes `errno`.  
  
## <a name="remarks"></a>Hinweise  
 Die `_controlfp_s`-Funktion ist eine plattformunabhängige und sicherere Version von `_control87`, die das Gleitkommasteuerwort in die in `currentControl` gespeicherte Adresse einsetzt und mithilfe von `newControl` festlegt. Die Bits in den Werten geben den Zustand des Gleitkommasteuerelements an. Mit dem Zustand des Gleitkommasteuerelements kann das Programm die Genauigkeits-, Rundungs- und Unendlichkeitsmodi im mathematischen Gleitkommapaket je nach Plattform ändern. Sie können auch `_controlfp_s` verwenden, um Gleitkommaausnahmen zu maskieren bzw. die Maskierung aufzuheben.  
  
 Wenn der Wert für `mask` gleich 0 ist, ruft `_controlfp_s` das Gleitkommasteuerwort ab und speichert den abgerufenen Wert in `currentControl`.  
  
 Wenn `mask` ungleich 0 ist, wird ein neuer Wert für das Steuerwort festgelegt: Für jedes festgelegte Bit (d. h. gleich 1) in `mask` wird das entsprechende Bit in `new` verwendet, um das Steuerwort zu aktualisieren. Das bedeutet: `fpcntrl` `=` ((`fpcntrl` `& ~mask`) &#124; (`new & mask`)) wobei `fpcntrl` das Gleitkommasteuerwort ist. In diesem Szenario ist `currentControl` nach Abschluss der Änderung auf den Wert festgelegt; es ist nicht der alte Bitwert des Steuerworts.  
  
> [!NOTE]
>  Standardmäßig maskieren die Laufzeitbibliotheken alle Gleitkommaausnahmen.  
  
 `_controlfp_s` ist nahezu identisch mit der `_control87`-Funktion auf Plattformen von Intel (x86), [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] und ARM. Wenn die Plattformen x86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] oder ARM Ihr Zielobjekt sind, können Sie `_control87` oder `_controlfp_s` verwenden.  
  
 Der Unterschied zwischen `_control87` und `_controlfp_s` besteht in dem Verarbeiten der `DENORMAL`-Werte. Für Intel (x86)-, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]- und ARM-Plattformen kann `_control87` die DENORMAL OPERAND-Ausnahmemaske festlegen und löschen. `_controlfp_s` ändert nicht die DENORMAL OPERAND-Ausnahmemaske. Dieses Beispiel veranschaulicht den Unterschied:  
  
```C  
_control87( _EM_INVALID, _MCW_EM );   
// DENORMAL is unmasked by this call.  
unsigned int current_word = 0;  
_controlfp_s( &current_word, _EM_INVALID, _MCW_EM );   
// DENORMAL exception mask remains unchanged.  
```  
  
 Die möglichen Werte für die Maskenkonstante (`mask`) und die neuen Steuerelementwerte (`newControl`) sind in der folgenden Hexadezimalwerttabelle aufgeführt. Verwenden die unten aufgeführten portablen Konstanten (`_MCW_EM`, `_EM_INVALID` usw.) als Argumente für diese Funktionen, anstatt den Hexadezimalwerten explizit anzugeben.  
  
 Von Intel (x86) abgeleitete Plattformen unterstützen die DENORMAL-Eingabe- und -Ausgabewerte in der Hardware. Das x86-Verhalten besteht darin, die DENORMAL-Werte beizubehalten. Die ARM-Plattform und die [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]-Plattformen mit SSE2-Unterstützung ermöglichen es, dass DENORMAL-Operanden und -Ergebnisse gelöscht werden oder dass Null erzwungen wird. Die Funktionen `_controlfp_s`, `_controlfp` und `_control87` stellen eine Maske zum Ändern dieses Verhaltens bereit. Das folgende Beispiel veranschaulicht die Verwendung dieser Maske:  
  
```C  
unsigned int current_word = 0;  
_controlfp_s(&current_word, _DN_SAVE, _MCW_DN);     
// Denormal values preserved on ARM platforms and on x64 processors with  
// SSE2 support. NOP on x86 platforms.  
_controlfp_s(&current_word, _DN_FLUSH, _MCW_DN);     
// Denormal values flushed to zero by hardware on ARM platforms   
// and x64 processors with SSE2 support. Ignored on other x86 platforms.  
```  
  
 Auf ARM-Plattformen gilt die `_controlfp_s`-Funktion für das FPSCR-Register. Auf [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]-Architekturen ist nur das SSE2-Steuerwort, das im MXCSR-Register gespeichert ist, betroffen. Auf Intel (x86)-Plattformen wirkt sich `_controlfp_s` sowohl bei x87 als auch bei SSE2 (sofern vorhanden) auf die Steuerworte aus. Es ist möglich, dass die zwei Steuerworte untereinander inkonsistent sind (z.B. aufgrund eines vorherigen Aufrufs von [__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)). Falls es eine Inkonsistenz zwischen den zwei Steuerworten gibt, legt `_controlfp_s` das `EM_AMBIGUOUS`-Flag in `currentControl` fest. Dies ist eine Warnung, dass das zurückgegebene Steuerwort den Zustand beider Gleitkommasteuerworte möglicherweise nicht genau dargestellt.  
  
 Auf der ARM- und der [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]-Architektur wird das Ändern des Unendlichkeitsmodus oder der Genauigkeit der Gleitkommawerte nicht unterstützt. Wenn die Genauigkeitssteuermaske auf der [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]-Plattform verwendet wird, führt die Funktion eine Assertion aus und der Handler für ungültige Parameter wird aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  
  
 Wenn die Maske nicht ordnungsgemäß festgelegt ist, generiert diese Funktion eine Ausnahme wegen eines ungültigen Parameters, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion `EINVAL` zurück und stellt `errno` auf `EINVAL` ein.  
  
 Diese Funktion wird ignoriert, wenn Sie [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) kompiliert, da die common Language Runtime (CLR) nur die standardmäßige Genauigkeit von Gleitkommawerten unterstützt.  
  
### <a name="mask-constants-and-values"></a>Maskenkonstanten und Werte  
  
 Durch das Aufheben der `_MCW_EM`-Maske wird die Ausnahme festgelegt, was die Hardwareausnahme ermöglicht. Das Festlegen der Maske blendet die Ausnahme aus. Wenn `_EM_UNDERFLOW` oder `_EM_OVERFLOW` auftritt, wird keine Hardwareausnahme ausgelöst, bis die nächste Gleitkommaanweisung ausgeführt wird. Um eine Hardwareausnahme direkt nach `_EM_UNDERFLOW` oder `_EM_OVERFLOW` zu generieren, rufen Sie die Anweisung FWAIT MASM auf.  
  
|Format|Farbtonwert|Konstante|Farbtonwert|  
|----------|---------------|--------------|---------------|  
|`_MCW_DN` (Nicht normale Steuerung)|0x03000000|`_DN_SAVE`<br /><br /> `_DN_FLUSH`|0x00000000<br /><br /> 0x01000000|  
|`_MCW_EM` (Unterbrechungsausnahmemaske)|0x0008001F|`_EM_INVALID`<br /><br /> `_EM_DENORMAL`<br /><br /> `_EM_ZERODIVIDE`<br /><br /> `_EM_OVERFLOW`<br /><br /> `_EM_UNDERFLOW`<br /><br /> `_EM_INEXACT`|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|  
|`_MCW_IC` (Unendlichkeitssteuerung)<br /><br /> (Wird auf ARM- oder [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]-Plattformen nicht unterstützt.)|0x00040000|`_IC_AFFINE`<br /><br /> `_IC_PROJECTIVE`|0x00040000<br /><br /> 0x00000000|  
|`_MCW_RC` (Rundungssteuerung)|0x00000300|`_RC_CHOP`<br /><br /> `_RC_UP`<br /><br /> `_RC_DOWN`<br /><br /> `_RC_NEAR`|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|  
|`_MCW_PC` (Genauigkeitssteuerung)<br /><br /> (Wird auf ARM- oder [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]-Plattformen nicht unterstützt.)|0x00030000|`_PC_24` (24 Bits)<br /><br /> `_PC_53` (53 Bits)<br /><br /> `_PC_64` (64 Bits)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_controlfp_s`|\<float.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```C  
// crt_contrlfp_s.c  
// processor: x86  
// This program uses _controlfp_s to output the FP control   
// word, set the precision to 24 bits, and reset the status to   
// the default.  
  
#include <stdio.h>  
#include <float.h>  
#pragma fenv_access (on)  
  
int main( void )  
{  
    double a = 0.1;  
    unsigned int control_word;  
    int err;  
  
    // Show original FP control word and do calculation.  
    err = _controlfp_s(&control_word, 0, 0);  
    if ( err ) /* handle error here */;  
  
    printf( "Original: 0x%.4x\n", control_word );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
  
    // Set precision to 24 bits and recalculate.  
    err = _controlfp_s(&control_word, _PC_24, MCW_PC);  
    if ( err ) /* handle error here */;  
  
    printf( "24-bit:   0x%.4x\n", control_word );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
  
    // Restore default precision-control bits and recalculate.  
    err = _controlfp_s(&control_word, _CW_DEFAULT, MCW_PC);  
    if ( err ) /* handle error here */;  
  
    printf( "Default:  0x%.4x\n", control_word );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
}  
```  
  
```Output  
Original: 0x9001f  
0.1 * 0.1 = 1.000000000000000e-002  
24-bit:   0xa001f  
0.1 * 0.1 = 9.999999776482582e-003  
Default:  0x9001f  
0.1 * 0.1 = 1.000000000000000e-002  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [_clear87, _clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [_status87, _statusfp, _statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)   
 [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)
