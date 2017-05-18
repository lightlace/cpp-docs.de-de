---
title: _mbsnbicmp, _mbsnbicmp_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsnbicmp_l
- _mbsnbicmp
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
- _strnicmp
- _wcsnicmp_l
- _mbsnbicmp
- mbsnbicmp
- mbsnbicmp_l
- _tcsnicmp
- _strnicmp_l
- _tcsnicmp_l
- _wcsnicmp
- _mbsnbicmp_l
dev_langs:
- C++
helpviewer_keywords:
- _tcsnicmp_l function
- _strnicmp function
- mbsnbicmp_l function
- _wcsnicmp_l function
- _mbsnbicmp function
- _mbsnbicmp_l function
- _tcsnicmp function
- _strnicmp_l function
- mbsnbicmp function
- _wcsnicmp function
ms.assetid: ddb44974-8b0c-42f0-90d0-56c9350bae0c
caps.latest.revision: 16
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 3eff360605f782a2a159195a91dfc3d97da2cb8a
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="mbsnbicmp-mbsnbicmpl"></a>_mbsnbicmp, _mbsnbicmp_l
Vergleicht `n` Bytes von zwei Multibyte-Zeichenfolgen und ignoriert die Groß- und Kleinschreibung.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
int _mbsnbicmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `string1, string2`  
 Zu vergleichende mit NULL endende Zeichenfolgen.  
  
 `count`  
 Anzahl der zu vergleichenden Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert gibt die Beziehung zwischen den untergeordneten Zeichenfolgen an.  
  
|Rückgabewert|Beschreibung|  
|------------------|-----------------|  
|< 0|Die untergeordnete Zeichenfolge `string1` ist kleiner als die untergeordnete Zeichenfolge `string2`.|  
|0|Die untergeordnete Zeichenfolge `string1` ist mit der untergeordneten Zeichenfolge `string2` identisch.|  
|> 0|Die untergeordnete Zeichenfolge `string1` ist größer als die untergeordnete Zeichenfolge `string2`.|  
  
 Bei einem Fehler gibt `_mbsnbcmp` `_NLSCMPERROR` zurück (definiert in String.h und Mbstring.h).  
  
## <a name="remarks"></a>Hinweise  
 Die `_mbsnbicmp`-Funktion führt einen Ordinalvergleich von höchstens der ersten `count` Bytes von `string1` und `string2` durch. Der Vergleich wird ausgeführt, indem jedes Zeichen in Kleinbuchstaben konvertiert wird; `_mbsnbcmp` ist eine Version von `_mbsnbicmp`, bei der die Groß-/Kleinschreibung beachtet wird. Der Vergleich endet, wenn in jeder Zeichenfolge beendende NULL-Zeichen erreicht wird, bevor `count` Zeichen verglichen wurden. Wenn beim Erreichen des beendenden NULL-Zeichens die Zeichenfolgen gleich sind, bevor `count` Zeichen verglichen wurden, ist die kürzere Zeichenfolge kleiner.  
  
 `_mbsnbicmp` ähnelt `_mbsnicmp`, mit dem Unterschied, dass die Zeichenfolgen nicht nach Zeichen, sondern nach `count`-Bytes verglichen werden.  
  
 Abhängig von der Großschreibung ist der Vergleich von zwei Zeichenfolgen mit Zeichen zwischen „Z“ und „a“ in der ASCII-Tabelle ('[', '\\', ']', '^', '_' und '\`') unterschiedlich. Beispielsweise werden die beiden Zeichenfolgen "`ABCDE`" und "`ABCD^`" in eine Richtung verglichen, wenn Kleinschreibung vorliegt ("`abcde`" > "`abcd^`") und in die andere Richtung, wenn Großschreibung vorliegt ("`ABCDE`" < "`ABCD^`").  
  
 `_mbsnbicmp` erkennt Multibyte-Zeichenfolgen gemäß der aktuellen [Multibyte-Codepage](../../c-runtime-library/code-pages.md). Die aktuelle Gebietsschemaeinstellung nimmt dabei keinen Einfluss.  
  
 Wenn `string1` oder `string2` ein NULL-Zeiger ist, ruft `_mbsnbicmp` den Handler für ungültige Parameter auf, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt die Funktion `_NLSCMPERROR` zurück und setzt `errno` auf `EINVAL`.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tcsnicmp`|`_strnicmp`|`_mbsnbicmp`|`_wcsnicmp`|  
|`_tcsnicmp_l`|`_strnicmp_l`|`_mbsnbicmp_l`|`_wcsnicmp_l`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_mbsnbicmp`|<mbstring.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
 Weitere Informationen finden Sie im Beispiel [_mbsnbcmp _mbsnbcmp_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [_mbsnbcat, _mbsnbcat_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [_mbsnbcmp, _mbsnbcmp_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)
