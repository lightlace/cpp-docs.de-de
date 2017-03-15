---
title: "_fpclass _fpclassf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fpclass"
  - "_fpclassf"
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
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "fpclass"
  - "_fpclass"
  - "_fpclassf"
  - "math/_fpclass"
  - "float/_fpclass"
  - "math/_fpclassf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fpclass-Funktion"
  - "Gleitkommazahlen, IEEE-Darstellung"
  - "_fpclass-Funktion"
  - "_fpclassf-Funktion"
ms.assetid: 2774872d-3543-446f-bc72-db85f8b95a6b
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _fpclass _fpclassf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt einen Wert, der die Gleitkommazahl Klassifizierung des Arguments zurück.  
  
## Syntax  
  
```  
int _fpclass(   
   double x   
);  
  
int _fpclassf(   
   float x   
); /* x64 only */  
```  
  
#### Parameter  
 `x`  
 Der zu testende Gleitkommawert.  
  
## Rückgabewert  
 Die `_fpclass` und `_fpclassf` Funktionen geben einen ganzzahligen Wert, der die Gleitkommazahl Klassifizierung des Arguments angibt zurück `x`. Die Klassifizierung möglicherweise die folgenden Werte, die in \< float.h \> definiert.  
  
|Wert|Beschreibung|  
|----------|------------------|  
|`_FPCLASS_SNAN`|Signaling\-NaN|  
|`_FPCLASS_QNAN`|Stiller NaN|  
|`_FPCLASS_NINF`|Minus unendlich \(INF\)|  
|`_FPCLASS_NN`|Negative normalisiert ungleich null|  
|`_FPCLASS_ND`|Negative denormalisiert|  
|`_FPCLASS_NZ`|Negative 0 \(null\) \(– 0\)|  
|`_FPCLASS_PZ`|Positive 0 \(\+ 0\)|  
|`_FPCLASS_PD`|Positive denormalisiert|  
|`_FPCLASS_PN`|Positive Werte ungleich NULL normalisiert|  
|`_FPCLASS_PINF`|Plus unendlich \(\+ INF\-Datei\)|  
  
## Hinweise  
 Die `_fpclass` und `_fpclassf` Funktionen sind Microsoft\-spezifisch. Sie sind vergleichbar mit [Fpclassify](../../c-runtime-library/reference/fpclassify.md), jedoch detaillierte Informationen über das Argument zurück. Die `_fpclassf` Funktion ist nur verfügbar, wenn die X64 Plattform.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`_fpclass`|\<float.h\>|  
  
 Weitere Informationen zur Kompatibilität und Konformität, finden Sie unter [Compatibility](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [IsNaN, \_isnan, \_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)   
 [fpclassify](../../c-runtime-library/reference/fpclassify.md)