---
title: isleadbyte, _isleadbyte_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _isleadbyte_l
- isleadbyte
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _istleadbyte
- _isleadbyte_l
- isleadbyte
dev_langs:
- C++
helpviewer_keywords:
- lead bytes
- _isleadbyte_l function
- _istleadbyte function
- istleadbyte function
- isleadbyte function
ms.assetid: 3b2bcf09-d82b-4803-9e80-59d04942802a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 82c8f6eb81e96527c0955d9b19fd8ce931e8d7fe
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="isleadbyte-isleadbytel"></a>isleadbyte, _isleadbyte_l
Bestimmt, ob ein Zeichen das führende Byte eines Multibytezeichens ist.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [CRT-Funktionen, die in universellen Windows-Plattform-apps nicht unterstützt](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
int isleadbyte(  
   int c   
);  
int _isleadbyte_l(  
   int c   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `c`  
 Zu testende ganze Zahl.  
  
## <a name="return-value"></a>Rückgabewert  
 `isleadbyte` gibt einen Wert ungleich 0 zurück, wenn das Argument die Testbedingung erfüllt, bzw. 0, wenn es sie nicht erfüllt. Im Gebietsschema "C" und in Einzelbyte-Zeichensatz(SBCS)-Gebietsschemas, gibt `isleadbyte` immer 0 zurück.  
  
## <a name="remarks"></a>Hinweise  
 Das Makro `isleadbyte` gibt einen Wert ungleich 0 (null) zurück, wenn dessen Argument das erste Byte eines Multibytezeichens ist. `isleadbyte` erzeugt ein aussagekräftiges Ergebnis für ein Ganzzahlargument von – 1 (`EOF`) zu `UCHAR_MAX` (0xFF) inklusive.  
  
 Der erwartete Argumenttyp von `isleadbyte` ist `int`. Ein mit Vorzeichen übergebenes Zeichen wird vom Compiler möglicherweise durch Vorzeichenerweiterung in eine ganze Zahl konvertiert, was zu unvorhersehbaren Ergebnissen führt.  
  
 Die Version dieser Funktion mit dem `_l` -Suffix ist beinahe identisch, verwendet jedoch das an sie übergebene Gebietsschema anstelle des aktuellen Gebietsschemas für ihr vom Gebietsschema abhängiges Verhalten.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_istleadbyte`|Gibt immer "false" zurück|**_** `isleadbyte`|Gibt immer "false" zurück|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`isleadbyte`|\<ctype.h>|  
|`_isleadbyte_l`|\<ctype.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Byteklassifizierung](../../c-runtime-library/byte-classification.md)   
 [Gebietsschema](../../c-runtime-library/locale.md)   
 [_ismbb-Routinen](../../c-runtime-library/ismbb-routines.md)