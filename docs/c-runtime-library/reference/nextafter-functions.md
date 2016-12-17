---
title: "Nextafter Nextafterf Nextafterl _nextafter _nextafterf Nexttoward Nexttowardf, nexttowardl"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "nextafterf"
  - "_nextafterf"
  - "nextafter"
  - "nextafterl"
  - "_nextafter"
  - "nexttoward"
  - "nexttowardf"
  - "nexttowardl"
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
  - "nextafter"
  - "_nextafter"
  - "nextafterf"
  - "nextafterl"
  - "_nextafterf"
  - "math/nextafter"
  - "math/nextafterf"
  - "math/nextafterl"
  - "nexttoward"
  - "nexttowardf"
  - "nexttowardl"
  - "math/nexttoward"
  - "math/nexttowardf"
  - "math/nexttowardl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_nextafter-Funktion"
  - "nextafter-Funktion"
  - "_nextafterf-Funktion"
  - "nextafterf-Funktion"
  - "Nextafterl-Funktion"
  - "Nexttoward-Funktion"
  - "Nexttowardf-Funktion"
  - "Nexttowardl-Funktion"
ms.assetid: 9785bfb9-de53-4bd0-9637-f05fa0c1f6ab
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# Nextafter Nextafterf Nextafterl _nextafter _nextafterf Nexttoward Nexttowardf, nexttowardl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt den nächsten darstellbaren Gleitkomma\-Wert zurück.  
  
## Syntax  
  
```  
double nextafter(  
   double x,  
   double y   
);  
  
float nextafter(  
   float x,  
   float y   
); /* C++ only, requires <cmath> */  
  
long double nextafter(  
   long double x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
float nextafterf(  
   float x,  
   float y   
);   
  
long double nextafterl(  
   long double x,  
   long double y   
);  
  
double _nextafter(  
   double x,  
   double y   
);  
  
float _nextafterf(  
   float x,  
   float y   
); /* x64 only */  
  
double nexttoward(  
   double x,  
   long double y   
);  
  
float nexttoward(  
   float x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
long double nexttoward(  
   long double x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
float nexttowardf(  
   float x,  
   long double y   
);   
  
long double nexttowardl(  
   long double x,  
   long double y   
);  
```  
  
#### Parameter  
 `x`  
 Der Gleitkommawert aus starten.  
  
 `y`  
 Der Gleitkommawert zu wechseln.  
  
## Rückgabewert  
 Gibt den nächsten darstellbaren Gleitkomma\-Wert des Rückgabetyps nach `x` in Richtung der `y`. Wenn `x`\=`y`, gibt die Funktion `y`, konvertiert in den Rückgabetyp mit keine Ausnahme ausgelöst. Wenn `x` stimmt nicht mit `y`, und das Ergebnis ist ein Denormal oder 0 \(null\), die FE\_UNDERFLOW und FE\_INEXACT Gleitkommaausnahme Status festgelegt sind und das richtige Ergebnis zurückgegeben wird. Wenn entweder `x` oder `y` eine NAN ist, dann ist der Rückgabewert eine mit der Eingabe NANs. Wenn `x` ist begrenzt und das Ergebnis ist, unendlich oder nicht in den Typ darstellbar ist, ein ordnungsgemäß signiertes unendlich oder NAN zurückgegeben wird, die FE\_OVERFLOW und FE\_INEXACT Gleitkommaausnahme Status festgelegt sind, und `errno` auf ERANGE festgelegt ist.  
  
## Hinweise  
 Die `nextafter` und `nexttoward` Funktion Familien sind gleichwertig, mit Ausnahme der Parametertyp der `y`. Wenn `x` und `y` gleich sind, ist der zurückgegebene Wert `y` in den Rückgabetyp konvertiert.  
  
 Da C\+\+ das Überladen zulässt, wenn Sie die \< Cmath \> einschließen können, rufen Sie Überladungen von `nextafter` und `nexttoward` zurückgegebene `float` und `long double` Typen. In einem C\-Programm `nextafter` und `nexttoward` jederzeit `double`.  
  
 Die `_nextafter` und `_nextafterf` Funktionen sind Microsoft\-spezifisch. Die `_nextafterf` Funktion ist nur verfügbar, wenn für X64 kompiliert.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header \(C\)|Erforderlicher Header \(C\+\+\)|  
|-------------|---------------------------------|-------------------------------------|  
|`nextafter`, `nextafterf`, `nextafterl`, `_nextafterf`, `nexttoward`, `nexttowardf`, `nexttowardl`|\<math.h\>|\<math.h\> oder \<cmath\>|  
|`_nextafter`|\<float.h\>|\< float.h \> oder \< Cfloat \>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [IsNaN, \_isnan, \_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)