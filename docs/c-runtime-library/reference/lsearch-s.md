---
title: _lsearch_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _lsearch_s
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
dev_langs: C++
helpviewer_keywords:
- linear searching
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- searching, linear
- _lsearch_s function
- lsearch_s function
ms.assetid: d2db0635-be7a-4799-8660-255f14450882
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a54af825a9b9b0f0ca36c2f733d5df85d808a13a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
|`NULL`|any|any|any|any|`EINVAL`|  
|any|`NULL`|any|!= 0|any|`EINVAL`|  
|any|any|any|any|Null|`EINVAL`|  
|any|any|`NULL`|ein|alle|`EINVAL`|  
  
## <a name="remarks"></a>Hinweise  
 Die `_lsearch_s`-Funktion führt eine lineare Suche nach dem Wert `key` in einem Array aus `num`-Elementen durch, die jeweils aus `width`-Bytes bestehen. Im Gegensatz zu `bsearch_s` muss bei `_lsearch_s` kein Array sortiert werden. Wenn `key` nicht gefunden wird, dann fügt `_lsearch_s` es am Ende des Arrays hinzu und inkrementiert `num`.  
  
 Die `compare`-Funktion ist ein Zeiger auf eine benutzerdefinierte Routine, die zwei Elemente des Arrays vergleicht und einen Wert zurückgibt, der die Beziehung angibt. Die `compare`-Funktion übernimmt auch den Zeiger auf den Kontext als erstes Argument. `_lsearch_s` ruft `compare` einmal oder mehrere Male während der Suche auf, wodurch bei jedem Aufruf Zeiger auf zwei Array-Elemente übergeben werden. `compare` muss die Elemente vergleichen und entweder ungleich null (d.h. die Elemente unterscheiden sich) oder 0 (d.h. die Elemente sind identisch) zurückgeben.  
  
 Der `context`-Zeiger kann nützlich sein, wenn die durchsuchte Datenstruktur Teil eines Objekts ist und die `compare`-Funktion auf Member des Objekts zugreifen muss. Beispielsweise kann Code in der `compare`-Funktion den void-Zeiger in den passenden Objekttyp umwandeln und auf Member des Objekts zugreifen. Die Hinzufügung des `context`-Zeigers macht `_lsearch_s` sicherer, da weiterer Kontext verwendet werden kann, um Fehler beim erneuten Eintreten zu vermeiden, die mit der Verwendung statischer Variablen zur Bereitstellung von Daten für die `compare`-Funktion einhergehen können.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_lsearch_s`|\<search.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [Suchen und Sortieren](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch_s](../../c-runtime-library/reference/bsearch-s.md)   
 [_lfind_s](../../c-runtime-library/reference/lfind-s.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)