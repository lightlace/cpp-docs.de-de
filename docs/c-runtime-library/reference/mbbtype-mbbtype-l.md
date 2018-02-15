---
title: _mbbtype, _mbbtype_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _mbbtype
- _mbbtype_l
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
- _mbbtype_l
- mbbtype
- mbbtype_l
- _mbbtype
dev_langs:
- C++
helpviewer_keywords:
- _mbbtype function
- _mbbtype_l function
- mbbtype function
- mbbtype_l function
ms.assetid: b8e34b40-842a-4298-aa39-0bd2d8e51c2a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: beaa8e11b8593205dd192547097e6f7228625410
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="mbbtype-mbbtypel"></a>_mbbtype, _mbbtype_l
Gibt den Bytetyp basierend auf dem vorherigen Byte zurück.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [CRT-Funktionen, die in universellen Windows-Plattform-apps nicht unterstützt](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
int _mbbtype(  
   unsigned char c,  
   int type   
);  
int _mbbtype_l(  
   unsigned char c,  
   int type,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `c`  
 Das zu überprüfende Zeichen.  
  
 `type`  
 Der Typ des zu prüfenden Bytes.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 `_mbbtype` gibt den Bytetyp in einer Zeichenfolge zurück. Diese Entscheidung ist kontextabhängig, wie durch den Wert von `type` angegeben, der die Steuerelement-Testbedingung bereitstellt. `type` ist der Typ des vorherigen Byte in der Zeichenfolge. Die Manifestkonstanten in der folgenden Tabelle sind in Mbctype.h definiert.  
  
|Wert von `type`|`_mbbtype` testet auf|Rückgabewert|`c`|  
|---------------------|--------------------------|------------------|---------|  
|Einen beliebiger Wert außer 1|Gültiges Einzelbyte oder führendes Byte|`_MBC_SINGLE` (0)|Single-Byte (0 x 20 – 0x7E, 0xA1 – 0xDF)|  
|Einen beliebiger Wert außer 1|Gültiges Einzelbyte oder führendes Byte|`_MBC_LEAD` (1)|Führendes Byte des multibytezeichens (0 x 81 – 0x9F, 0xE0 – 0xFC)|  
|Einen beliebiger Wert außer 1|Gültiges Einzelbyte oder führendes Byte|`_MBC_ILLEGAL`<br /><br /> ( -1)|Ungültiges Zeichen (jeder Wert außer 0 x 20 – 0x7E, 0xA1 – 0xDF, 0 x 81 – 0x9F, 0xE0 – 0xFC|  
|1|Gültiges nachfolgendes Byte|`_MBC_TRAIL` (2)|Nachfolgendes Byte des multibytezeichens (0 x 40 – 0x7E, 0 x 80 – 0xFC)|  
|1|Gültiges nachfolgendes Byte|`_MBC_ILLEGAL`<br /><br /> ( -1)|Ungültiges Zeichen (jeder Wert außer 0 x 20 – 0x7E, 0xA1 – 0xDF, 0 x 81 – 0x9F, 0xE0 – 0xFC|  
  
## <a name="remarks"></a>Hinweise  
 Die `_mbbtype`-Funktion bestimmt den Typ eines Bytes in einem Multibytezeichen. Wenn der Wert von `type` ein beliebiger Wert außer 1 ist, testet `_mbbtype` auf ein gültiges Einzelbyte oder führendes Byte eines Multibytezeichens. Wenn der Wert von `type` 1 lautet, testet `_mbbtype` auf ein gültiges nachfolgendes Byte eines Multibytezeichens.  
  
 Der Ausgabewert ist von der `LC_CTYPE`-Kategorieeinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Die `_mbbtype`-Version dieser Funktion verwendet das aktuelle Gebietsschema auf dieses vom Gebietsschema abhängige Verhalten. Die `_mbbtype_l`-Version ist beinahe identisch, abgesehen davon, dass es stattdessen den ihr übergebenen Gebietsschemaparameter verwendet. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 In früheren Versionen hieß `_mbbtype`  `chkctype`. Verwenden Sie bei neuem Code stattdessen `_mbbtype`.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------|---------------------|  
|`_mbbtype`|\<mbstring.h>|\<mbctype.h>*|  
|`_mbbtype_l`|\<mbstring.h>|\<mbctype.h>*|  
  
 \* Für Definitionen von Manifestkonstanten, die als Rückgabewerte verwendet werden.  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Byteklassifizierung](../../c-runtime-library/byte-classification.md)