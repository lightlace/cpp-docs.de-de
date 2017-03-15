---
title: _lsearch_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _lsearch_s
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _lsearch_s
- lsearch_s
dev_langs:
- C++
helpviewer_keywords:
- linear searching
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- searching, linear
- _lsearch_s function
- lsearch_s function
ms.assetid: d2db0635-be7a-4799-8660-255f14450882
caps.latest.revision: 17
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 6f89899e5fe2c00cf17a7a18c9de2eac2ba8462f
ms.lasthandoff: 02/24/2017

---
# <a name="lsearchs"></a>_lsearch_s
Führt eine lineare Suche für einen Wert aus. Eine Version von [_lsearch](../../c-runtime-library/reference/lsearch.md) mit Sicherheitserweiterungen, so wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## <a name="syntax"></a>Syntax  
  
```  
void *_lsearch_s(  
   const void *key,  
   void *base,  
   unsigned int *num,  
   size_t size,  
   int (__cdecl *compare)(void *, const void *, const void *),  
   void * context  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `key`  
 Das Objekt, nach dem gesucht werden soll.  
  
 `base`  
 Zeiger auf der Basis des zu durchsuchenden Arrays.  
  
 `num`  
 Anzahl der Elemente.  
  
 `size`  
 Die Größe jedes Array-Elements in Bytes.  
  
 `compare`  
 Ein Zeiger auf die Vergleichsroutine. Der zweite Parameter ist ein Zeiger auf den Schlüssel für die Suche. Der dritte Parameter ist ein Zeiger auf das Arrayelement, das mit dem Schlüssel verglichen werden soll.  
  
 `context`  
 Ein Zeiger auf ein Objekt, auf das in der Vergleichsfunktion möglicherweise zugegriffen werden kann.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn `key` gefunden wird, gibt `_lsearch_s` einen Zeiger auf das Element des Arrays bei `base` zurück, das `key` entspricht. Wenn `key` nicht gefunden wird, gibt `_lsearch_s` einen Zeiger auf das neu hinzugefügte Element am Ende des Arrays zurück.  
  
 Wenn ungültige Parameter an die Funktion übergeben werden, ruft sie den Handler für ungültige Parameter auf, wie in [Parameter Validation (Parametervalidierung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `NULL`zurück. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|`key`|`base`|`compare`|`num`|`size`|`errno`|  
|-----------|------------|---------------|-----------|------------|-------------|  
|`NULL`|alle|alle|alle|alle|`EINVAL`|  
|alle|`NULL`|alle|!= 0|alle|`EINVAL`|  
|alle|alle|alle|any|Null|`EINVAL`|  
|any|alle|`NULL`|ein|alle|`EINVAL`|  
  
## <a name="remarks"></a>Hinweise  
 Die `_lsearch_s`-Funktion führt eine lineare Suche nach dem Wert `key` in einem Array aus `num`-Elementen durch, die jeweils aus `width`-Bytes bestehen. Im Gegensatz zu `bsearch_s`, muss bei `_lsearch_s` kein Array sortiert werden. Wenn `key` nicht gefunden wird, dann fügt `_lsearch_s` es am Ende des Arrays hinzu und inkrementiert `num`.  
  
 Die `compare`-Funktion ist ein Zeiger auf eine benutzerdefinierte Routine, die zwei Elemente des Arrays vergleicht und einen Wert zurückgibt, der die Beziehung angibt. Die `compare`-Funktion übernimmt auch den Zeiger auf den Kontext als erstes Argument. `_lsearch_s` ruft `compare` einmal oder mehrere Male während der Suche auf, wodurch bei jedem Aufruf Zeiger auf zwei Array-Elemente übergeben werden. `compare` muss die Elemente vergleichen und entweder ungleich null (d.h. die Elemente unterscheiden sich) oder 0 (d.h. die Elemente sind identisch) zurückgeben.  
  
 Der `context`-Zeiger kann nützlich sein, wenn die durchsuchte Datenstruktur Teil eines Objekts ist und die `compare`-Funktion auf Member des Objekts zugreifen muss. Beispielsweise kann Code in der `compare`-Funktion den void-Zeiger in den passenden Objekttyp umwandeln und auf Member des Objekts zugreifen. Die Hinzufügung des `context`-Zeigers macht `_lsearch_s` sicherer, da weiterer Kontext verwendet werden kann, um Fehler beim erneuten Eintreten zu vermeiden, die mit der Verwendung statischer Variablen zur Bereitstellung von Daten für die `compare`-Funktion einhergehen können.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_lsearch_s`|\<search.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Suchen und Sortieren](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch_s](../../c-runtime-library/reference/bsearch-s.md)   
 [_lfind_s](../../c-runtime-library/reference/lfind-s.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)
