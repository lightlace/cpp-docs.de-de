---
title: "_ecvt_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ecvt_s"
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
  - "ecvt_s"
  - "_ecvt_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ecvt_s-Funktion"
  - "Konvertieren doppelter Zahlen"
  - "ecvt_s-Funktion"
  - "Zahlen, Konvertieren"
ms.assetid: d52fb0a6-cb91-423f-80b3-952a8955d914
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# _ecvt_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert `double` eine Zahl in eine Zeichenfolge.  Dies ist eine Version von [\_ecvt](../../c-runtime-library/reference/ecvt.md) mit werden, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
errno_t _ecvt_s(   
   char * _Buffer,  
   size_t _SizeInBytes,  
   double _Value,  
   int _Count,  
   int *_Dec,  
   int *_Sign  
);  
template <size_t size>  
errno_t _ecvt_s(   
   char (&_Buffer)[size],  
   double _Value,  
   int _Count,  
   int *_Dec,  
   int *_Sign  
); // C++ only  
```  
  
#### Parameter  
 \[out\] `_Buffer`  
 Ausgefüllt den Mauszeiger zur Zeichenfolge der Ziffern, das Ergebnis der Konvertierung.  
  
 \[in\] `_SizeInBytes`  
 Größe des Puffers in Bytes.  
  
 \[in\] `_Value`  
 Zu konvertierende Zahl.  
  
 \[in\] `_Count`  
 Zahl Ziffern gespeichert.  
  
 \[out\] `_Dec`  
 Gespeicherte Kommastellung.  
  
 \[out\] `_Sign`  
 Zeichen der konvertierten Zahl.  
  
## Rückgabewert  
 Null wenn erfolgreich.  Der Rückgabewert ist ein Fehlercode, wenn ein Fehler auftritt.  Fehlercodes werden in Errno.h definiert.  Weitere Informationen finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Bei einer ungültigen Parameters, wie in der folgenden Tabelle aufgeführt, ruft diese Funktion den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt `EINVAL` zurück.  
  
### Fehlerbedingungen  
  
|`_Buffer`|`_SizeInBytes`|\_Value|\_Count|\_Dec|\_Sign|Rückgabewert|Wert in `buffer`|  
|---------------|--------------------|-------------|-------------|-----------|------------|------------------|----------------------|  
|`NULL`|any|any|any|any|any|`EINVAL`|Nicht geändert.|  
|Nicht `NULL` \(Punkte zum gültigen Arbeitsspeicher\)|\<\=0|any|any|any|any|`EINVAL`|Nicht geändert.|  
|any|any|any|any|`NULL`|any|`EINVAL`|Nicht geändert.|  
|any|any|any|any|any|`NULL`|`EINVAL`|Nicht geändert.|  
  
 **Sicherheitsprobleme**  
  
 `_ecvt_s` generierte kann eine Zugriffsverletzung, wenn `buffer` nicht auf gültigen Arbeitsspeicher wird und nicht `NULL` ist.  
  
## Hinweise  
 Die `_ecvt_s`\-Funktion konvertiert eine Gleitkommazahl zu einer Zeichenfolge.  Der `_Value`\-Parameter ist die zu konvertierende, Gleitkommazahl.  Diese Funktion speichert bis `count` Ziffern von `_Value` als Zeichenfolge und fügt an ein NULL\-Zeichen \("\\ 0 "\).  Wenn die Anzahl der Ziffern in `_Value``_Count` überschreitet, wird die Ziffer niederwertige gerundet.  Wenn es weniger als Ziffern `count` gibt, wird die Zeichenfolge durch Nullen ergänzt.  
  
 Nur Ziffern sind in der Zeichenfolge gespeichert.  Die Position des Dezimaltrennzeichens und das Zeichen von `_Value` können von `_Dec` und `_Sign` nach dem Aufruf abgerufen werden.  Der `_Dec`\-Parameter zeigt auf einen ganzzahligen Wert, der die Position des Dezimaltrennzeichens in Bezug auf den Anfang der Zeichenfolge vorhanden sind.  0 oder ein ganzzahliger negativer Wert gibt an, dass das Dezimaltrennzeichen auf der linken Seite die erste Ziffer liegt.  Der `_Sign`\-Parameter zeigt auf eine ganze Zahl, die das Zeichen der konvertierten Zahl angibt.  Wenn der ganzzahlige Wert 0 ist, wird die Zahl positiv.  Andernfalls ist die Zahl negativ.  
  
 Ein Puffer der Länge `_CVTBUFSIZE` ist für jeden Gleitkommawert ausreichend.  
  
 Der Unterschied zwischen `_ecvt_s` und `_fcvt_s` ist in der Interpretation des Parameters `_Count`.  `_ecvt_s` interpretiert `_Count` während die Gesamtzahl der Stellen in der Ausgabezeichenfolge, während `_fcvt_s``_Count` als Anzahl von Ziffern nach dem Dezimaltrennzeichen interpretiert.  
  
 In C\+\+ unter Verwendung dieser Funktion wird durch eine Vorlagenüberladung vereinfacht; Überladung kann automatisch die Pufferlänge ableiten und die Anforderung nicht, einen Größenargument anzugeben.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
 Die Debugversion dieser Funktion wird zuerst den Puffer mit 0xFD aus.  Mit [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md) deaktivieren Sie dieses Verhalten.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|Optionaler Header|  
|--------------|---------------------------|-----------------------|  
|`_ecvt_s`|\<stdlib.h\>|\<errno.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// ecvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main( )  
{  
  char * buf = 0;  
  int decimal;  
  int sign;  
  int err;  
  
  buf = (char*) malloc(_CVTBUFSIZE);  
  err = _ecvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);  
  
  if (err != 0)  
  {  
     printf("_ecvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
  **Konvertierter Wert: 12000**   
## .NET Framework-Entsprechung  
 <xref:System.Convert.ToString*>  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [\_fcvt\_s](../../c-runtime-library/reference/fcvt-s.md)   
 [\_gcvt\_s](../../c-runtime-library/reference/gcvt-s.md)