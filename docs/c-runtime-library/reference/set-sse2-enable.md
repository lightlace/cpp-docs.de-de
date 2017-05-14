---
title: _set_SSE2_enable | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_SSE2_enable
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_SSE2_enable
- set_SSE2_enable
dev_langs:
- C++
helpviewer_keywords:
- _set_SSE2_enable function
- Streaming SIMD Extensions 2 instructions
- set_SSE2_enable function
ms.assetid: 55db895d-fc1e-475a-9110-b781a9bb51c5
caps.latest.revision: 19
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
ms.openlocfilehash: 6dcc32b981c73cda13152f82139a307e4739fe5c
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="setsse2enable"></a>_set_SSE2_enable
Aktiviert oder deaktiviert die Verwendung von [SIMD-Streamingerweiterungen 2](http://msdn.microsoft.com/en-us/f98440eb-73a9-4f96-b203-ac41bb6701ea)-Anweisungen (SSE2) mathematischen CRT-Routinen. (Diese Funktion ist nicht auf x64-Architekturen verfügbar, da SSE2 standardmäßig aktiviert ist.)  
  
## <a name="syntax"></a>Syntax  
  
```  
int _set_SSE2_enable(  
   int flag  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `flag`  
 1, um die SSE2-Implementierung zu aktivieren; 0, um die SSE2-Implementierung zu deaktivieren. Standardmäßig ist die SSE2-Implementierung auf Prozessoren aktiviert, die sie unterstützen.  
  
## <a name="return-value"></a>Rückgabewert  
 Wert ungleich null, wenn die SSE2-Implementierung aktiviert ist; 0, wenn die SSE2-Implementierung deaktiviert ist.  
  
## <a name="remarks"></a>Hinweise  
 Die folgenden Funktionen haben SSE2-Implementierungen, die mithilfe von `_set_SSE2_enable` aktiviert werden können:  
  
-   [atan](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)  
  
-   [ceil](../../c-runtime-library/reference/ceil-ceilf-ceill.md)  
  
-   [exp](../../c-runtime-library/reference/exp-expf.md)  
  
-   [floor](../../c-runtime-library/reference/floor-floorf-floorl.md)  
  
-   [log](../../c-runtime-library/reference/log-logf-log10-log10f.md)  
  
-   [log10](../../c-runtime-library/reference/log-logf-log10-log10f.md)  
  
-   [modf](../../c-runtime-library/reference/modf-modff-modfl.md)  
  
-   [pow](../../c-runtime-library/reference/pow-powf-powl.md)  
  
 Die SSE2-Implementierung dieser Funktionen unterscheiden sich möglicherweise geringfügig von den Standardimplementierungen, da SSE2-Zwischenwerte 64-Bit-Gleitkommamengen sind, aber die Zwischenwerte der Standardimplementierung 80-Bit-Gleitkommamengen sind.  
  
> [!NOTE]
>  Wenn Sie die Compileroption [/Oi (Systeminterne Funktionen erstellen)](../../build/reference/oi-generate-intrinsic-functions.md) verwenden, um das Projekt zu kompilieren, scheint `_set_SSE2_enable` möglicherweise keine Auswirkung zu haben. Die Compileroption `/Oi` gibt der Compiler die Berechtigung zum Verwenden von systeminternen Funktionen, um CRT-Aufrufe zu ersetzen; dieses Verhalten überschreibt die Auswirkung von `_set_SSE2_enable`. Wenn Sie sicherzustellen möchten, dass `/Oi` `_set_SSE2_enable` nicht außer Kraft setzt, kompilieren Sie Ihr Projekt mit `/Oi-`. Dies kann auch dann sinnvoll sein, wenn Sie andere Compilerswitches verwenden, die `/Oi` beinhalten.  
  
 Die SSE2-Implementierung wird nur verwendet, wenn alle Ausnahmen maskiert werden. Verwenden Sie [_control87, _controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md) zum Maskieren von Ausnahmen.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_set_SSE2_enable`|\<math.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_set_SSE2_enable.c  
// processor: x86  
#include <math.h>  
#include <stdio.h>  
  
int main()  
{  
   int i = _set_SSE2_enable(1);  
  
   if (i)  
      printf("SSE2 enabled.\n");  
   else  
      printf("SSE2 not enabled; processor does not support SSE2.\n");  
}  
```  
  
 **Ausgabe**  
  
 `SSE2 enabled.`  
  
## <a name="see-also"></a>Siehe auch  
 [CRT-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md)
