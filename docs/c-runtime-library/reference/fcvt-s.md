---
title: _fcvt_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fcvt_s
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
- fcvt_s
- _fcvt_s
dev_langs:
- C++
helpviewer_keywords:
- fcvt_s function
- converting floating point, to strings
- floating-point functions, converting number to string
- _fcvt_s function
ms.assetid: 48671197-1d29-4c2b-a5d8-d2368f5f68a1
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 9c282757ae79367cdc2ee72b3f3ce8d0e50983fa
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="fcvts"></a>_fcvt_s
Konvertiert eine Gleitkommazahl in eine Zeichenfolge. Dies ist eine sicherere Version von [_fcvt](../../c-runtime-library/reference/fcvt.md), wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 [out] `buffer`  
 Der angegebene Puffer, der das Ergebnis der Konvertierung enthält.  
  
 [in] `sizeInBytes`  
 Die Größe des Puffers in Byte.  
  
 [in] `value`  
 Zu konvertierende Zahl.  
  
 [in] `count`  
 Anzahl der Ziffern nach dem Dezimaltrennzeichen.  
  
 [out] `dec`  
 Zeiger auf die gespeicherte Position der Dezimalstelle.  
  
 [out] `sign`  
 Zeiger auf den gespeicherten Zeichen-Indikator.  
  
## <a name="return-value"></a>Rückgabewert  
 Null, wenn erfolgreich. Der Rückgabewert ist ein Fehlercode, wenn ein Fehler auftritt. Fehlercodes sind in Errno.h definiert. Eine Liste dieser Fehler finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Bei einem in der folgenden Tabelle enthaltenen ungültigen Parameter wird von dieser Funktion der Handler für ungültige Parameter aufgerufen, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt `EINVAL` zurück.  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|`buffer`|`sizeInBytes`|Wert|count|dec|sign|Return|Wert in `buffer`.|  
|--------------|-------------------|-----------|-----------|---------|----------|------------|-----------------------|  
|`NULL`|alle|alle|alle|alle|alle|`EINVAL`|Nicht geändert.|  
|Nicht `NULL` (zeigt gültigen Speicher an)|<=0|any|alle|alle|alle|`EINVAL`|Nicht geändert.|  
|any|alle|alle|alle|`NULL`|alle|`EINVAL`|Nicht geändert.|  
|any|alle|alle|alle|alle|`NULL`|`EINVAL`|Nicht geändert.|  
  
 **Sicherheitsprobleme**  
  
 `_fcvt_s` kann eine Zugriffsverletzung erzeugen, wenn `buffer` nicht auf einen gültigen Speicher zeigt und nicht `NULL` ist.  
  
## <a name="remarks"></a>Hinweise  
 Mit der `_fcvt_s`-Funktion werden Gleitkommazahlen in mit NULL endende Zeichenfolgen konvertiert. Der Parameter `value` ist die zu konvertierende Gleitkommazahl. `_fcvt_s` speichert die Ziffern von `value` als Zeichenfolge, und fügt das Zeichen NULL ('\0') an. Der `count`-Parameter gibt die Anzahl der zu speichernden Ziffern nach dem Dezimaltrennzeichen an. Überschüssige Ziffern werden auf `count` Stellen gerundet. Wenn weniger als `count` Dezimalstellen vorhanden sind, wird die Zeichenfolge mit Nullen aufgefüllt.  
  
 In der Zeichenfolge werden nur Ziffern gespeichert. Die Position der Dezimalstelle und das Vorzeichen von `value` können nach dem Aufruf aus `dec` und `sign` abgerufen werden. Der Parameter `dec` zeigt auf einen ganzzahligen Wert; dieser ganzzahlige Wert gibt die Position der Dezimalstelle im Verhältnis zum Anfang der Zeichenfolge an. Der Wert null oder ein negativer ganzzahliger Wert geben an, dass sich die Dezimalstelle links neben der ersten Ziffer befindet. Der Parameter `sign` verweist auf eine ganze Zahl, die das Vorzeichen von `value` angibt. Die ganze Zahl ist auf 0 festgelegt, wenn `value` positiv ist, und ist auf eine Zahl ungleich null festgelegt, wenn `value` negativ ist.  
  
 Ein Puffer der Länge `_CVTBUFSIZE` reicht für alle Gleitkommawerte aus.  
  
 `_ecvt_s` und `_fcvt_s` unterscheiden sich hinsichtlich der Interpretation des Parameters `count`. `_ecvt_s`interpretiert `count` als die Gesamtzahl der Ziffern in der Ausgabezeichenfolge und `_fcvt_s` interpretiert `count` als die Anzahl der Ziffern nach dem Dezimaltrennzeichen an.  
  
 Die Verwendung dieser Funktion in C++ wird durch eine Vorlagenüberladung vereinfacht. Eine Überladung kann automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
 Die Debugversion dieser Funktion füllt zunächst den Puffer mit „0xFD“ auf. Um dieses Verhalten zu deaktivieren, verwenden Sie [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|Optionaler Header|  
|--------------|---------------------|---------------------|  
|`_fcvt_s`|\<stdlib.h>|\<errno.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
 **Bibliotheken:** Alle Versionen der [CRT-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
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
  
```Output  
Converted value: 120000  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt_s](../../c-runtime-library/reference/ecvt-s.md)   
 [_gcvt_s](../../c-runtime-library/reference/gcvt-s.md)   
 [_fcvt](../../c-runtime-library/reference/fcvt.md)
