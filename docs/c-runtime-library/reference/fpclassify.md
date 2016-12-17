---
title: "fpclassify"
ms.custom: na
ms.date: "12/03/2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "fpclassify"
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
apitype: "HeaderDef"
f1_keywords: 
  - "fpclassify"
  - "math/fpclassify"
helpviewer_keywords: 
  - "Fpclassify-Makro"
  - "fpclassify-Funktion"
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "corob"
manager: "ghogen"
---
# fpclassify
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt die Gleitkommazahl Klassifizierung des Arguments zurück.  
  
## Syntax  
  
```  
int fpclassify(   
   /* floating-point */ x   
);  
  
int fpclassify(   
   float x   
); // C++ only  
  
int fpclassify(   
   double x   
); // C++ only  
  
int fpclassify(   
   long double x   
); // C++ only  
  
```  
  
#### Parameter  
 `x`  
 Der zu testende Gleitkommawert.  
  
## Rückgabewert  
 `fpclassify` Gibt einen ganzzahligen Wert, der die gleitkommaklasse des Arguments angibt `x`. Diese Tabelle zeigt die möglichen Rückgabewerte `fpclassify`, die in \< math.h \> definiert.  
  
|Wert|Beschreibung|  
|----------|------------------|  
|`FP_NAN`|Quiet, signalisieren oder unbestimmten NaN|  
|`FP_INFINITE`|Eine Plus oder minus unendlich|  
|`FP_NORMAL`|Eine positive oder negative normalisierten Wert ungleich null|  
|`FP_SUBNORMAL`|Eine positive oder negative denormalisierte Wert|  
|`FP_ZERO`|Eine Positive oder negative 0 \(null\)|  
  
## Hinweise  
 In C `fpclassify` ein Makro; in C\+\+ `fpclassify` ist eine Funktion überladen mit Argumenttypen der `float`, `double`, oder `long double`. In beiden Fällen hängt der zurückgegebene Wert und nicht auf alle zwischendarstellung der tatsächliche Typ des Expression\-Arguments. Z. B. eine normale `double` oder `long double` Wert kann werden unendlich, denormal oder NULL\-Wert bei der Konvertierung in einen `float`.  
  
## Anforderungen  
  
|Funktion\/Makro|Erforderlicher Header \(C\)|Erforderlicher Header \(C\+\+\)|  
|---------------------|---------------------------------|-------------------------------------|  
|`fpclassify`|\<math.h\>|\<math.h\> oder \<cmath\>|  
  
 Die `fpclassify` Makro und `fpclassify` Funktionen die C99\- und C \+\+ 11\-Spezifikationen entsprechen. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [IsNaN, \_isnan, \_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)