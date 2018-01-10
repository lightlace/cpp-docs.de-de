---
title: _ecvt_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _ecvt_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- ecvt_s
- _ecvt_s
dev_langs: C++
helpviewer_keywords:
- _ecvt_s function
- ecvt_s function
- numbers, converting
- converting double numbers
ms.assetid: d52fb0a6-cb91-423f-80b3-952a8955d914
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: af4b49b0fd0e4de74a3f454a544c07f08c89b81d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ecvts"></a>_ecvt_s
Konvertiert eine `double`-Zahl in eine Zeichenfolge. Dies ist eine sicherere Version von [_ecvt](../../c-runtime-library/reference/ecvt.md), wie unter [Security Features in the CRT (Sicherheitsfunktionen in der CRT)](../../c-runtime-library/security-features-in-the-crt.md) beschrieben wird.  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 [out] `_Buffer`  
 Wird mit dem Zeiger auf die Zeichenfolge mit Ziffern aufgefüllt, die sich aus der Konvertierung ergeben.  
  
 [in] `_SizeInBytes`  
 Größe des Puffers in Byte.  
  
 [in] `_Value`  
 Zu konvertierende Zahl.  
  
 [in] `_Count`  
 Anzahl der gespeicherten Ziffern.  
  
 [out] `_Dec`  
 Gespeicherte Position der Dezimalstelle.  
  
 [out] `_Sign`  
 Vorzeichen der konvertierten Zahl.  
  
## <a name="return-value"></a>Rückgabewert  
 Null, wenn erfolgreich. Der Rückgabewert ist ein Fehlercode, wenn ein Fehler auftritt. Fehlercodes sind in Errno.h definiert. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Bei einem in der folgenden Tabelle enthaltenen ungültigen Parameter wird von dieser Funktion der Handler für ungültige Parameter aufgerufen, wie unter [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt `EINVAL` zurück.  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|`_Buffer`|`_SizeInBytes`|_Value|_Count|_Dec|_Sign|Rückgabewert|Wert in `buffer`.|  
|---------------|--------------------|-------------|-------------|-----------|------------|------------------|-----------------------|  
|`NULL`|any|any|any|any|any|`EINVAL`|Nicht geändert.|  
|Nicht `NULL` (zeigt auf gültigen Speicher)|<=0|any|any|any|any|`EINVAL`|Nicht geändert.|  
|any|any|any|any|`NULL`|any|`EINVAL`|Nicht geändert.|  
|any|any|any|any|any|`NULL`|`EINVAL`|Nicht geändert.|  
  
 **Sicherheitsprobleme**  
  
 `_ecvt_s` kann eine Zugriffsverletzung erzeugen, wenn `buffer` nicht auf einen gültigen Speicher zeigt und nicht `NULL` ist.  
  
## <a name="remarks"></a>Hinweise  
 Mit der `_ecvt_s`-Funktion werden Gleitkommazahlen in Zeichenfolgen konvertiert. Der Parameter `_Value` ist die zu konvertierende Gleitkommazahl. Mit dieser Funktion werden bis zu `count` Ziffern von `_Value` als Zeichenfolge gespeichert und das Zeichen NULL ('\0') angefügt. Wenn in `_Value` mehr als `_Count` Zeichen vorhanden sind, wird die untere Ziffer gerundet. Wenn weniger als `count` Ziffern vorhanden sind, wird die Zeichenfolge mit Nullen aufgefüllt.  
  
 In der Zeichenfolge werden nur Ziffern gespeichert. Die Position der Dezimalstelle und das Vorzeichen von `_Value` können nach dem Aufruf aus `_Dec` und `_Sign` abgerufen werden. Der Parameter `_Dec` zeigt auf einen Integer-Wert, der die Position der Dezimalstelle im Verhältnis zum Zeichenfolgenanfang angibt. Der Wert 0 oder ein negativer Integer-Wert geben an, dass sich die Dezimalstelle links neben der ersten Ziffer befindet. Der Parameter `_Sign` zeigt auf einn Integer-Wert, der das Vorzeichen der konvertierten Zahl angibt. Wenn der Integer-Wert 0 ist, ist die Zahl positiv. Andernfalls ist die Zahl negativ.  
  
 Ein Puffer der Länge `_CVTBUFSIZE` reicht für alle Gleitkommawerte aus.  
  
 `_ecvt_s` und `_fcvt_s` unterscheiden sich hinsichtlich der Interpretation des Parameters `_Count`. Von `_ecvt_s` wird `_Count` als die Gesamtanzahl der Ziffern in der Ausgabezeichenfolge interpretiert, während `_Count` von `_fcvt_s` als die Anzahl der Ziffern nach der Dezimalstelle interpretiert wird.  
  
 Die Verwendung dieser Funktion in C++ wird durch eine Vorlagenüberladung vereinfacht. Eine Überladung kann automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
 Die Debugversion dieser Funktion füllt zunächst den Puffer mit „0xFD“ auf. Um dieses Verhalten zu deaktivieren, verwenden Sie [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|Optionaler Header|  
|--------------|---------------------|---------------------|  
|`_ecvt_s`|\<stdlib.h>|\<errno.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
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
  
```Output  
Converted value: 12000  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Floating-Point Support (Gleitkommaunterstützung)](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [_fcvt_s](../../c-runtime-library/reference/fcvt-s.md)   
 [_gcvt_s](../../c-runtime-library/reference/gcvt-s.md)