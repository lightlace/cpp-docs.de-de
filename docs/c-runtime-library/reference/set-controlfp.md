---
title: _set_controlfp | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_controlfp
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
- set_controlfp
- _set_controlfp
dev_langs: C++
helpviewer_keywords:
- set_controlfp function
- floating-point functions, setting control word
- _set_controlfp function
ms.assetid: e0689d50-f68a-4028-a9c1-fb23eedee4ad
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0f738b643ac225df45b063839f2f758b2766e5d0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="setcontrolfp"></a>_set_controlfp
Legt das Gleitkommasteuerwort fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __cdecl _set_controlfp(  
    unsigned int newControl,  
    unsigned int mask  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `newControl`  
 Neue Bitwerte des Steuerworts.  
  
 `mask`  
 Maske für festzulegende neue Steuerwortbits.  
  
## <a name="return-value"></a>Rückgabewert  
 Keine.  
  
## <a name="remarks"></a>Hinweise  
 `_set_controlfp` ähnelt `_control87`, setzt aber nur das Gleitkommasteuerwort auf `newControl`. Die Bits in den Werten geben den Zustand des Gleitkommasteuerelements an. Über den Gleitkommawert-Steuerstatus kann das Programm die Modi für Genauigkeit, Rundung und Unendlichkeit im Paket für Gleitkommaoperationen ändern. Sie können auch `_set_controlfp` verwenden, um Gleitkommaausnahmen zu maskieren bzw. die Maskierung aufzuheben. Weitere Informationen finden Sie unter [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md).  
  
 Diese Funktion ist veraltet, beim Kompilieren mit [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) , da die common Language Runtime nur die standardmäßige Genauigkeit von Gleitkommawerten unterstützt.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|Kompatibilität|  
|-------------|---------------------|-------------------|  
|`_set_controlfp`|\<float.h>|Nur x86-Prozessor|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [_clear87, _clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [_status87, _statusfp, _statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)