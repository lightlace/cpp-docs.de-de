---
title: _control87, _controlfp, __control87_2 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _control87
- _controlfp
- __control87_2
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
- _control87
- __control87_2
- control87
- _controlfp
- controlfp
- control87_2
- _control87_2
dev_langs:
- C++
helpviewer_keywords:
- floating-point numbers, control word
- _control87 function
- control87 function
- controlfp function
- _controlfp function
- __control87_2 function
- floating-point functions, setting control word
- floating-point functions
- EM_AMBIGUOUS
- control87_2 function
ms.assetid: 0d09729d-d9a0-43d6-864c-43ff25e7e0c5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d2405b569c7e7accb828ba7052a9ea9fae125f0a
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="control87-controlfp-control872"></a>_control87, _controlfp, __control87_2
Ruft das Gleitkommasteuerwort ab und legt es fest. Eine sicherere Version von `_controlfp` ist verfügbar. Informationen dazu finden Sie unter [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned int _control87(   
   unsigned int new,  
   unsigned int mask   
);  
unsigned int _controlfp(   
   unsigned int new,  
   unsigned int mask   
);  
int __control87_2(  
   unsigned int new,  
   unsigned int mask,  
   unsigned int* x86_cw,  
   unsigned int* sse2_cw  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `new`  
 Neue Bitwerte des Steuerworts.  
  
 `mask`  
 Maske für festzulegende neue Steuerwortbits.  
  
 `x86_cw`  
 Gefüllt mit dem Steuerwort für die x87-Gleitkommaeinheit. Übergeben Sie 0 (`NULL`), um nur das SSE2-Steuerwort festzulegen.  
  
 `sse2_cw`  
 Steuerwort für die SSE-Gleitkommaeinheit. Übergeben Sie 0 (`NULL`), um nur das x87-Steuerwort festzulegen.  
  
## <a name="return-value"></a>Rückgabewert  
 Für `_control87` und `_controlfp` geben die Bits im zurückgegebenen Wert den Zustand des Gleitkommasteuerelements an. Eine vollständige Definition der Bits, die von `_control87` zurückgegeben werden, finden Sie in FLOAT.H.  
  
 Für `__control87_2` ist der Rückgabewert 1, was den Erfolg angibt.  
  
## <a name="remarks"></a>Hinweise  
 Die `_control87`-Funktion ruft das Gleitkommasteuerwort ab und legt es fest. Mit dem Gleitkommasteuerwort kann das Programm die Genauigkeits-, Rundungs- und Unendlichkeitsmodi im mathematischen Gleitkommapaket je nach Plattform ändern. Sie können auch `_control87` verwenden, um Gleitkommaausnahmen zu maskieren bzw. die Maskierung aufzuheben. Wenn der Wert für `mask` gleich 0 ist, ruft `_control87` das Gleitkommasteuerwort ab. Wenn `mask` ungleich 0 ist, wird ein neuer Wert für das Steuerwort festgelegt: Für jedes aktivierte Bit (d. h. gleich 1) in `mask` wird das entsprechende Bit in `new` verwendet, um das Steuerwort zu aktualisieren. Das bedeutet: `fpcntrl` `=` ((`fpcntrl` `& ~mask`) &#124; (`new & mask`)) wobei `fpcntrl` das Gleitkommasteuerwort ist.  
  
> [!NOTE]
>  Standardmäßig maskieren die Laufzeitbibliotheken alle Gleitkommaausnahmen.  
  
 `_controlfp` ist eine plattformunabhängige, portable Version von `_control87`. Es ist nahezu identisch mit der `_control87`-Funktion auf Intel (x86)-, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]- und ARM-Plattformen. Wenn die Plattformen x86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] oder ARM Ihr Zielobjekt sind, verwenden Sie `_control87` oder `_controlfp`.  
  
 Der Unterschied zwischen `_control87` und `_controlfp` besteht im Verarbeiten der DENORMAL-Werte. Für Intel (x86)-, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]- und ARM-Plattformen kann `_control87` die DENORMAL OPERAND-Ausnahmemaske festlegen und löschen. `_controlfp` ändert nicht die DENORMAL OPERAND-Ausnahmemaske. Dieses Beispiel veranschaulicht den Unterschied:  
  
```  
_control87( _EM_INVALID, _MCW_EM );   
// DENORMAL is unmasked by this call  
_controlfp( _EM_INVALID, _MCW_EM );   
// DENORMAL exception mask remains unchanged  
```  
  
 Die möglichen Werte für die Maskenkonstante (`mask`) und die neuen Steuerelementwerte (`new`) sind in der folgenden Hexadezimalwerttabelle aufgeführt. Verwenden Sie die unten aufgeführten portablen Konstanten (`_MCW_EM`, `_EM_INVALID` usw.) als Argumente für diese Funktionen, anstatt die Hexadezimalwerte explizit anzugeben.  
  
 Von Intel (x86) abgeleitete Plattformen unterstützen die DENORMAL-Eingabe- und -Ausgabewerte in der Hardware. Das x86-Verhalten besteht darin, die DENORMAL-Werte beizubehalten. Die ARM-Plattform und die [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]-Plattformen mit SSE2-Unterstützung ermöglichen es, dass DENORMAL-Operanden und -Ergebnisse gelöscht werden oder dass Null erzwungen wird. Die Funktionen `_controlfp` und `_control87` stellen eine Maske zum Ändern dieses Verhaltens bereit. Das folgende Beispiel veranschaulicht die Verwendung dieser Maske.  
  
```  
_controlfp(_DN_SAVE, _MCW_DN);     
// Denormal values preserved on ARM platforms and on x64 processors with  
// SSE2 support. NOP on x86 platforms.  
_controlfp(_DN_FLUSH, _MCW_DN);     
// Denormal values flushed to zero by hardware on ARM platforms   
// and x64 processors with SSE2 support. Ignored on other x86 platforms.  
```  
  
 Auf ARM-Plattformen sind die Funktionen `_control87` und `_controlfp` auf das FPSCR-Register anwendbar. Auf [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]-Architekturen ist nur das SSE2-Steuerwort, das im MXCSR-Register gespeichert ist, betroffen. Auf Intel (x86)-Plattformen wirken sich `_control87` und `_controlfp` sowohl bei x87 als auch bei SSE2 (sofern vorhanden) auf die Steuerworte aus. Die Funktion `__control87_2` ermöglicht es, dass die x87- und die SSE2-Gleitkommaeinheiten zusammen oder getrennt gesteuert werden. Wenn dies für beide Einheiten gelten soll, übergeben Sie die Adressen von zwei ganzen Zahlen an `x86_cw` und `sse2_cw`. Wenn dies nur für eine Einheit gelten soll, übergeben Sie eine Adresse für diesen Parameter, aber 0 (NULL) für den anderen. Wenn 0 für einen dieser Parameter übergeben wird, hat die Funktion keine Auswirkungen auf diese Gleitkommaeinheit. Diese Funktionalität kann in Situationen nützlich sein, in denen ein Teil des Codes die x87-Gleitkommaeinheit und ein anderer Teil des Codes die SSE2-Gleitkommaeinheit verwendet. Wenn Sie `__control87_2` in einem Teil eines Programms verwenden und verschiedene Werte für die Gleitkommasteuerworte festlegen und dann `_control87` oder `_controlfp` verwenden, um das Steuerwort weiter zu bearbeiten, können `_control87` und `_controlfp` möglicherweise kein einzelnes Steuerwort zurückgeben, um den Zustand beider Gleitkommaeinheiten darzustellen. In diesem Fall legen diese Funktionen das `EM_AMBIGUOUS`-Flag im zurückgegebenen ganzzahligen Wert fest, um anzugeben, dass eine Inkonsistenz zwischen den beiden Steuerworten besteht. Dies ist eine Warnung, dass das zurückgegebene Steuerwort den Zustand beider Gleitkommasteuerworte möglicherweise nicht genau dargestellt.  
  
 Auf der ARM- und der [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]-Architektur wird das Ändern des Unendlichkeitsmodus oder der Genauigkeit der Gleitkommawerte nicht unterstützt. Wenn die Genauigkeitssteuermaske auf der [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]-Plattform verwendet wird, führt die Funktion eine Assertion aus und der Handler für ungültige Parameter wird aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  
  
> [!NOTE]
>  `__control87_2` wird auf der ARM- oder [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]-Architektur nicht unterstützt. Wenn Sie `__control87_2` verwenden und Ihr Programm für die ARM- oder die [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]-Architektur kompilieren, generiert der Compiler einen Fehler.  
  
 Diese Funktionen werden ignoriert, wenn Sie [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) kompiliert, da die common Language Runtime (CLR) nur die standardmäßige Genauigkeit von Gleitkommawerten unterstützt.  
  
 **Hexadezimalwerte**  
  
 Durch das Aufheben der `_MCW_EM`-Maske wird die Ausnahme festgelegt, was die Hardwareausnahme ermöglicht. Das Festlegen der Maske blendet die Ausnahme aus. Wenn `_EM_UNDERFLOW` oder `_EM_OVERFLOW` auftritt, wird keine Hardwareausnahme ausgelöst, bis die nächste Gleitkommaanweisung ausgeführt wird. Um eine Hardwareausnahme direkt nach `_EM_UNDERFLOW` oder `_EM_OVERFLOW` zu generieren, rufen Sie die Anweisung `FWAIT` MASM auf.  
  
|Format|Farbtonwert|Konstante|Farbtonwert|  
|----------|---------------|--------------|---------------|  
|`_MCW_DN` (Nicht normale Steuerung)|0x03000000|`_DN_SAVE`<br /><br /> `_DN_FLUSH`|0x00000000<br /><br /> 0x01000000|  
|`_MCW_EM` (Unterbrechungsausnahmemaske)|0x0008001F|`_EM_INVALID`<br /><br /> `_EM_DENORMAL`<br /><br /> `_EM_ZERODIVIDE`<br /><br /> `_EM_OVERFLOW`<br /><br /> `_EM_UNDERFLOW`<br /><br /> `_EM_INEXACT`|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|  
|`_MCW_IC` (Unendlichkeitssteuerung)<br /><br /> (Wird auf ARM- oder [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]-Plattformen nicht unterstützt.)|0x00040000|`_IC_AFFINE`<br /><br /> `_IC_PROJECTIVE`|0x00040000<br /><br /> 0x00000000|  
|`_MCW_RC` (Rundungssteuerung)|0x00000300|`_RC_CHOP`<br /><br /> `_RC_UP`<br /><br /> `_RC_DOWN`<br /><br /> `_RC_NEAR`|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|  
|`_MCW_PC` (Genauigkeitssteuerung)<br /><br /> (Wird auf ARM- oder [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]-Plattformen nicht unterstützt.)|0x00030000|`_PC_24` (24 Bits)<br /><br /> `_PC_53` (53 Bits)<br /><br /> `_PC_64` (64 Bits)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_control87`, `_controlfp`, `_control87_2`|\<float.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```C  
// crt_cntrl87.c  
// processor: x86  
// This program uses __control87_2 to output the x87 control   
// word, set the precision to 24 bits, and reset the status to   
// the default.  
  
#include <stdio.h>  
#include <float.h>  
#pragma fenv_access (on)  
  
int main( void )  
{  
    double a = 0.1;  
    unsigned int control_word_x87;  
  
    // Show original x87 control word and do calculation.  
    control_word_x87 = __control87_2(0, 0,  
                                     &control_word_x87, 0);  
    printf( "Original: 0x%.4x\n", control_word_x87 );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
  
    // Set precision to 24 bits and recalculate.  
    control_word_x87 = __control87_2(_PC_24, MCW_PC,  
                                     &control_word_x87, 0);  
    printf( "24-bit:   0x%.4x\n", control_word_x87 );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
  
    // Restore default precision-control bits and recalculate.  
    control_word_x87 = __control87_2( _CW_DEFAULT, MCW_PC,   
                                     &control_word_x87, 0 );  
    printf( "Default:  0x%.4x\n", control_word_x87 );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
}  
```  
  
```Output  
Original: 0x0001  
0.1 * 0.1 = 1.000000000000000e-002  
24-bit:   0x0001  
0.1 * 0.1 = 9.999999776482582e-003  
Default:  0x0001  
0.1 * 0.1 = 1.000000000000000e-002  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Floating-Point Support (Gleitkommaunterstützung)](../../c-runtime-library/floating-point-support.md)   
 [_clear87, _clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [_status87, _statusfp, _statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)   
 [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md)