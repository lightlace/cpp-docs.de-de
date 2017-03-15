---
title: "_fcvt_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fcvt_s"
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
  - "fcvt_s"
  - "_fcvt_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fcvt_s-Funktion"
  - "Konvertieren von Gleitkommazahlen, zu Zeichenfolgen"
  - "fcvt_s-Funktion"
  - "Gleitkommafunktionen, Konvertieren einer Zahl in eine Zeichenfolge"
ms.assetid: 48671197-1d29-4c2b-a5d8-d2368f5f68a1
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# _fcvt_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert eine Gleitkommazahl zu einer Zeichenfolge.  Dies ist eine Version von [\_fcvt](../../c-runtime-library/reference/fcvt.md) mit werden, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
errno_t _fcvt_s(   
   char* buffer,  
   size_t sizeInBytes,  
   double value,  
   int count,  
   int *dec,  
   int *sign   
);  
template <size_t size>  
errno_t _fcvt_s(   
   char (&buffer)[size],  
   double value,  
   int count,  
   int *dec,  
   int *sign   
); // C++ only  
```  
  
#### Parameter  
 \[out\] `buffer`  
 Der angegebenen Puffer, der das Ergebnis der Konvertierung enthält.  
  
 \[in\] `sizeInBytes`  
 Die Größe des Puffers in Bytes.  
  
 \[in\] `value`  
 Zu konvertierende Zahl.  
  
 \[in\] `count`  
 Anzahl der Ziffern nach dem Dezimalkomma.  
  
 \[out\] `dec`  
 Zeiger zur gespeicherten Kommastellung.  
  
 \[out\] `sign`  
 Zeiger zum gespeicherten Zeichenindikator.  
  
## Rückgabewert  
 Null wenn erfolgreich.  Der Rückgabewert ist ein Fehlercode, wenn ein Fehler auftritt.  Fehlercodes werden in Errno.h definiert.  Eine Liste dieser Fehler, finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Bei einer ungültigen Parameters, wie in der folgenden Tabelle aufgeführt, ruft diese Funktion den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt `EINVAL` zurück.  
  
### Fehlerbedingungen  
  
|`buffer`|`sizeInBytes`|Wert|count|Dezember|sign|Return|Wert in `buffer`|  
|--------------|-------------------|----------|-----------|--------------|----------|------------|----------------------|  
|`NULL`|any|any|any|any|any|`EINVAL`|Nicht geändert.|  
|Nicht `NULL` \(Punkte zum gültigen Arbeitsspeicher\)|\<\=0|any|any|any|any|`EINVAL`|Nicht geändert.|  
|any|any|any|any|`NULL`|any|`EINVAL`|Nicht geändert.|  
|any|any|any|any|any|`NULL`|`EINVAL`|Nicht geändert.|  
  
 **Sicherheitsprobleme**  
  
 `_fcvt_s` generierte kann eine Zugriffsverletzung, wenn `buffer` nicht auf gültigen Arbeitsspeicher wird und nicht `NULL` ist.  
  
## Hinweise  
 Die `_fcvt_s`\-Funktion konvertiert eine Gleitkommazahl zu einer auf NULL endende Zeichenfolge.  Der `value`\-Parameter ist die zu konvertierende, Gleitkommazahl.  `_fcvt_s` speichert die Ziffern von `value` als Zeichenfolge und fügt an ein NULL\-Zeichen \("\\ 0 "\).  Der `count`\-Parameter gibt die Anzahl der nach dem Dezimaltrennzeichen an zu speichernden Ziffern.  Überschüssige Ziffern werden `count` weg zu Stellen gerundet.  Wenn es weniger als `count` Ziffern von Genauigkeit gibt, wird die Zeichenfolge durch Nullen ergänzt.  
  
 Nur Ziffern sind in der Zeichenfolge gespeichert.  Die Position des Dezimaltrennzeichens und das Zeichen von `value` können von `dec` und `sign` nach dem Aufruf abgerufen werden.  Der `dec`\-Parameter zeigt auf einen ganzzahligen Wert; dieser ganzzahlige Wert gibt die Position des Dezimaltrennzeichens in Bezug auf den Anfang der Zeichenfolge.  Ein null oder negative ganzzahliger Wert gibt an, dass das Dezimaltrennzeichen auf der linken Seite die erste Ziffer liegt.  Der Parameter `sign` zeigt auf eine ganze Zahl, die das Zeichen von `value` angibt.  Die ganze Zahl wird 0 festgelegt, wenn `value` gleich ist und wird auf eine Zahl ungleich 0 \(null\) festgelegt, wenn `value` negativ ist.  
  
 Ein Puffer der Länge `_CVTBUFSIZE` ist für jeden Gleitkommawert ausreichend.  
  
 Der Unterschied zwischen `_ecvt_s` und `_fcvt_s` ist in der Interpretation des Parameters `count`.  `_ecvt_s` interpretiert `count`, während die Gesamtzahl der Stellen in der Ausgabezeichenfolge und c `_fcvt_s``ount` als Anzahl von Ziffern nach dem Dezimaltrennzeichen interpretiert.  
  
 In C\+\+ unter Verwendung dieser Funktion wird durch eine Vorlagenüberladung vereinfacht; Überladung kann automatisch die Pufferlänge ableiten und die Anforderung nicht, einen Größenargument anzugeben.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
 Die Debugversion dieser Funktion wird zuerst den Puffer mit 0xFD aus.  Mit [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md) deaktivieren Sie dieses Verhalten.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|Optionaler Header|  
|--------------|---------------------------|-----------------------|  
|`_fcvt_s`|\<stdlib.h\>|\<errno.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
 **Bibliotheken:** Alle Versionen der [CRT\-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// fcvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
  char * buf = 0;  
  int decimal;  
  int sign;  
  int err;  
  
  buf = (char*) malloc(_CVTBUFSIZE);  
  err = _fcvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);  
  
  if (err != 0)  
  {  
     printf("_fcvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
  **Konvertierter Wert: 120000**   
## .NET Framework-Entsprechung  
 <xref:System.Convert.ToString*>  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_ecvt\_s](../../c-runtime-library/reference/ecvt-s.md)   
 [\_gcvt\_s](../../c-runtime-library/reference/gcvt-s.md)   
 [\_fcvt](../../c-runtime-library/reference/fcvt.md)