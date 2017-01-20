---
title: "_gcvt_s"
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
  - "_gcvt_s"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_gcvt_s"
  - "gcvt_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CVTBUFSIZE"
  - "_gcvt_s-Funktion"
  - "Konvertierungen, Gleitkommawerte zu Zeichenfolgen"
  - "CVTBUFSIZE"
  - "Gleitkommafunktionen, Konvertieren einer Zahl in eine Zeichenfolge"
  - "gcvt_s-Funktion"
  - "Zahlen, Konvertieren in Zeichenfolgen"
  - "Zeichenfolgen [C++], Konvertieren aus Gleitkommazahl"
ms.assetid: 0a8d8a26-5940-4ae3-835e-0aa6ec1b0744
caps.latest.revision: 30
caps.handback.revision: "28"
ms.author: "corob"
manager: "ghogen"
---
# _gcvt_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert einen Gleitkommawert in eine Zeichenfolge.  Dies ist eine Version von [\_gcvt](../../c-runtime-library/reference/gcvt.md) mit werden, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
errno_t _gcvt_s(   
   char *buffer,  
   size_t sizeInBytes,  
   double value,  
   int digits   
);  
template <size_t cchStr>  
errno_t _gcvt_s(   
   char (&buffer)[cchStr],  
   double value,  
   int digits   
); // C++ only  
```  
  
#### Parameter  
 \[out\] `buffer`  
 Puffer, um das Ergebnis der Konvertierung zu speichern.  
  
 \[in\] `sizeInBytes`  
 Größe des Puffers.  
  
 \[in\] `value`  
 Der zu konvertierende Wert.  
  
 \[in\] `digits`  
 Anzahl der signifikanten Ziffern gespeichert.  
  
## Rückgabewert  
 Null wenn erfolgreich.  Wenn ein Fehler aufgrund eines ungültigen Parameters \(siehe folgende Tabelle für ungültige Werte\), auftritt, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, wird ein Fehlercode zurückgegeben.  Fehlercodes werden in Errno.h definiert.  Eine Liste dieser Fehler, finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### Fehlerbedingungen  
  
|`buffer`|`sizeInBytes`|`value`|`digits`|Return|Wert in `buffer`|  
|--------------|-------------------|-------------|--------------|------------|----------------------|  
|`NULL`|any|any|any|`EINVAL`|Nicht geändert.|  
|Nicht `NULL` \(Punkte zum gültigen Arbeitsspeicher\)|0 \(Null\)|any|any|`EINVAL`|Nicht geändert.|  
|Nicht `NULL` \(Punkte zum gültigen Arbeitsspeicher\)|any|any|\>\= `sizeInBytes`|`EINVAL`|Nicht geändert.|  
  
 **Sicherheitsprobleme**  
  
 `_gcvt_s` kann eine Zugriffsverletzung generiert, wenn `buffer` nicht auf gültigen Arbeitsspeicher wird und nicht `NULL` ist.  
  
## Hinweise  
 Die `_gcvt_s`\-Funktion konvertiert ein Gleitkommawert `value` als Zeichenfolge \(die ein Dezimaltrennzeichen und ein beliebiges Zeichenbyte enthält\) und die Zeichenfolge in `buffer`.  `buffer` sollte so groß sein, den konvertierten Wert sowie ein NULL anzupassen, das automatisch angefügt wird.  Ein Puffer der Länge `_CVTBUFSIZE` ist für jeden Gleitkommawert ausreichend.  Wenn eine Puffergröße von `digits` \+ 1 verwendet wird, überschreibt die Funktion nicht das Ende des Puffers, daher ist sicher, einen ausreichenden Puffer für diesen Vorgang bereitzustellen.  `_gcvt_s` versucht, `digits` Ziffern im Dezimalformat zu erzeugen.  Wenn das nicht der Fall ist, erzeugt es `digits` Ziffern im exponentiellen Format.  Nachfolgende Nullen in der Konvertierung können unterdrückt werden.  
  
 In C\+\+ unter Verwendung dieser Funktion wird durch eine Vorlagenüberladung vereinfacht; Überladung kann automatisch die Pufferlänge ableiten und die Anforderung nicht, einen Größenargument anzugeben.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
 Die Debugversion dieser Funktion wird zuerst den Puffer mit 0xFD aus.  Mit [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md) deaktivieren Sie dieses Verhalten.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_gcvt_s`|\<stdlib.h\>|\<error.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_gcvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
  char buf[_CVTBUFSIZE];  
  int decimal;  
  int sign;  
  int err;  
  
  err = _gcvt_s(buf, _CVTBUFSIZE, 1.2, 5);  
  
  if (err != 0)  
  {  
     printf("_gcvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
  **Konvertierter Wert: 1,2**   
## .NET Framework-Entsprechung  
 <xref:System.Convert.ToString*>  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_ecvt\_s](../../c-runtime-library/reference/ecvt-s.md)   
 [\_fcvt\_s](../../c-runtime-library/reference/fcvt-s.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)