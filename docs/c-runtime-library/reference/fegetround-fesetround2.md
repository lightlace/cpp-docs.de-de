---
title: "fegetround, fesetround"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "fegetround"
  - "fesetround"
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
  - "fegetround"
  - "fesetround"
  - "fenv/fegetround"
  - "fenv/fesetround"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "fegetround-Funktion"
  - "fesetround-Funktion"
ms.assetid: 596af00b-be2f-4f57-b2f5-460485f9ff0b
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# fegetround, fesetround
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den aktuellen Gleitkomma\-Rundungsmodus ab bzw. legt ihn fest.  
  
## Syntax  
  
```  
int fegetround(void);  
  
int fesetround(  
   int round_mode  
);   
```  
  
#### Parameter  
 `round_mode`  
 Der als eines der Gleitkomma\-Rundungsmakros festzulegende Rundungsmodus. Wenn der Wert keinem der Gleitkomma\-Rundungsmakros entspricht, wird der Rundungsmodus nicht geändert.  
  
## Rückgabewert  
 Bei Erfolg gibt `fegetround` den Rundungsmodus als einen der Gleitkomma\-Rundungsmakrowerte zurück. Ein negativer Wert wird zurückgegeben, wenn der aktuelle Rundungsmodus nicht bestimmt werden kann.  
  
 Bei Erfolg gibt `fesetround` 0 \(null\) zurück. Andernfalls wird ein Wert ungleich null zurückgegeben.  
  
## Hinweise  
 Gleitkommaoperationen können mehrere Rundungsmodi verwenden. Diese steuern, in welche Richtung die Ergebnisse von Gleitkommaoperationen beim Speichern der Ergebnisse gerundet werden. Hiermit werden die Namen und das Verhalten der in \<fenv.h\> definierten Gleitkomma\-Rundungsmakros angegeben:  
  
|Makro|Beschreibung|  
|-----------|------------------|  
|FE\_DOWNWARD|Runden in Richtung minus unendlich.|  
|FE\_TONEAREST|Runden in Richtung des nächsten Werts.|  
|FE\_TOWARDZERO|Runden in Richtung 0 \(null\).|  
|FE\_UPWARD|Runden in Richtung plus unendlich.|  
  
 Das Standardverhalten von FE\_TONEAREST ist, Ergebnisse in der Mitte zwischen darstellbaren Werten auf den nächsten Wert mit einem geraden \(0\) LSB \(Least Significant Bit, niedrigstwertiges Bit\) zu runden.  
  
 Der aktuelle Rundungsmodus wirkt sich auf diese Vorgänge aus:  
  
-   Zeichenfolgenkonvertierungen.  
  
-   Die Ergebnisse der arithmetischen Gleitkommaoperatoren außerhalb konstanter Ausdrücke.  
  
-   Die Rundungsfunktionen der Bibliothek, wie z. B. `rint` und `nearbyint`.  
  
-   Rückgabewerte aus mathematischen Funktionen der Standardbibliothek.  
  
 Der aktuelle Rundungsmodus wirkt sich auf diese Vorgänge nicht aus:  
  
-   Die Bibliotheksfunktionen `trunc`, `ceil`, `floor` und `lround`.  
  
-   Implizite Umwandlungen und Konvertierungen von Gleitkommazahl in ganze Zahl, bei denen immer in Richtung 0 \(null\) gerundet wird.  
  
-   Die Ergebnisse von arithmetischen Gleitkommaoperatoren in konstanten Ausdrücken, bei denen immer auf den nächsten Wert gerundet wird.  
  
 Um diese Funktionen zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)`\-Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv\_access](../../preprocessor/fenv-access.md).  
  
## Anforderungen  
  
|Funktion|C\-Header|C\+\+\-Header|  
|--------------|---------------|-------------------|  
|`fegetround`, `fesetround`|\<fenv.h\>|\<cfenv\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [Nearbyint, Nearbyintf, nearbyintl](../../c-runtime-library/reference/nearbyint-nearbyintf-nearbyintl1.md)   
 [rint, rintf, rintl](../../c-runtime-library/reference/rint-rintf-rintl.md)   
 [Lrint, Lrintf, Lrintl, Llrint, Llrintf, llrintl](../../c-runtime-library/reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)