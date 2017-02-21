---
title: "_set_controlfp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_controlfp"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "set_controlfp"
  - "_set_controlfp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_controlfp-Funktion"
  - "Gleitkommafunktionen, Festlegen des Steuerworts"
  - "set_controlfp-Funktion"
ms.assetid: e0689d50-f68a-4028-a9c1-fb23eedee4ad
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _set_controlfp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt das Gleitkommasteuerwort fest.  
  
## Syntax  
  
```  
void __cdecl _set_controlfp(  
    unsigned int newControl,  
    unsigned int mask  
);  
```  
  
#### Parameter  
 `newControl`  
 Neue Bitwerte des Steuerworts.  
  
 `mask`  
 Maske für festzulegende neue Steuerwortbits.  
  
## Rückgabewert  
 Keine.  
  
## Hinweise  
 `_set_controlfp` ähnelt `_control87`, jedoch wird nur das Gleitkommasteuerwort auf `newControl` fest.  Die Bits in den Werten geben den Zustand des Gleitkommasteuerelements an.  Der Gleitkommasteuerelementzustand ermöglicht dem Programm, um die Genauigkeit, das Runden und die Unendlichkeitsmodi im mathematischen GleitkommaPaket zu ändern.  Sie können Gleitkommaausnahmen auch mit `_set_controlfp` oder entlarven maskieren.  Weitere Informationen finden Sie unter [\_control87, \_controlfp, \_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md).  
  
 Diese Funktion wird bei Kompilierung mit [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md) oder `/clr:pure` veraltet, da Common Language Runtime nur die Standardgleitkommagenauigkeit unterstützt.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Kompatibilität|  
|-------------|---------------------------|--------------------|  
|`_set_controlfp`|\<float.h\>|nur x86\-Prozessor|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [\_clear87, \_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [\_status87, \_statusfp, \_statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)