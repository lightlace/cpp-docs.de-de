---
title: _ismbclegal, _ismbclegal_l, _ismbcsymbol, _ismbcsymbol_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbclegal_l
- _ismbclegal
- _ismbcsymbol
- _ismbcsymbol_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- ismbcsymbol_l
- _ismbcsymbol_l
- _ismbcsymbol
- _ismbclegal_l
- _ismbclegal
- ismbclegal_l
- ismbcsymbol
- ismbclegal
dev_langs: C++
helpviewer_keywords:
- ismbcsymbol function
- ismbclegal_l function
- _istlegal_l function
- istlegal function
- _istlegal function
- _ismbcsymbol function
- _ismbclegal_l function
- ismbclegal function
- ismbcsymbol_l function
- _ismbclegal function
- _ismbcsymbol_l function
- istlegal_l function
ms.assetid: 31bf1ea5-b56f-4e28-b21e-b49a2cf93ffc
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 057b6ee50934561662becbcf258910ee292664ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ismbclegal-ismbclegall-ismbcsymbol-ismbcsymboll"></a>_ismbclegal, _ismbclegal_l, _ismbcsymbol, _ismbcsymbol_l
Überprüft, ob ein Multibytezeichen ein gültiges Zeichen oder ein Symbolzeichen ist.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
int _ismbclegal(  
   unsigned int c   
);  
int _ismbclegal_l(  
   unsigned int c,   
   _locale_t locale  
);  
int _ismbcsymbol(  
   unsigned int c   
);  
int _ismbcsymbol_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `c`  
 Zu testende Zeichen.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede dieser Routinen gibt einen Wert ungleich 0 zurück, wenn das Zeichen die Testbedingung erfüllt, bzw. 0, wenn es sie nicht erfüllt. Wenn `c`<= 255 ist und es eine entsprechende `_ismbb`-Routine gibt (beispielsweise `_ismbcalnum` entspricht `_ismbbalnum`), ist das Ergebnis der Rückgabewert der entsprechenden `_ismbb`-Routine.  
  
## <a name="remarks"></a>Hinweise  
 Jede dieser Funktionen testet ein angegebenes Mehrbytezeichen auf eine angegebene Bedingung.  
  
 Die Versionen dieser Funktionen mit dem `_l`-Suffix sind beinahe identisch, verwenden jedoch das ihnen übergebene Gebietsschema anstelle des aktuellen Gebietsschemas für ihr vom Gebietsschema abhängiges Verhalten. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
|-Routine zurückgegebener Wert|Testbedingung|Beispiel für Codepage 932|  
|-------------|--------------------|---------------------------|  
|`_ismbclegal`|Gültiges Multibyte|Gibt einen Wert ungleich 0 (null) nur dann zurück, wenn das erste Byte von `c` im Bereich 0x81-0x9F oder 0xE0-0xFC liegt, während das zweite Byte im Bereich 0x40-0x7E oder 0x80-FC liegt.|  
|`_ismbcsymbol`|Multibytesymbol|Gibt nur dann einen Wert ungleich null zurück, wenn 0x8141<=`c`<=0x81AC ist.|  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_istlegal`|Gibt immer "false" zurück|`_ismbclegal`|Gibt immer false zurück.|  
|`_istlegal_l`|Gibt immer "false" zurück|`_ismbclegal_l`|Gibt immer false zurück.|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_ismbclegal,_ismbclegal_l`|\<mbstring.h>|  
|`_ismbcsymbol,_ismbcsymbol_l`|\<mbstring.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenklassifizierung](../../c-runtime-library/character-classification.md)   
 [_ismbc-Routinen](../../c-runtime-library/ismbc-routines.md)   
 [is- und isw-Routinen](../../c-runtime-library/is-isw-routines.md)   
 [_ismbb-Routinen](../../c-runtime-library/ismbb-routines.md)