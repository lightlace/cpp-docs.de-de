---
title: _lsearch_s | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
ms.workload:
- cplusplus
ms.openlocfilehash: 21d2aface59c4c2fd4247d299af26c63cdf46d45
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="lsearchs"></a>_lsearch_s

Führt eine lineare Suche für einen Wert aus. Eine Version von [_lsearch](lsearch.md) mit Sicherheitserweiterungen, so wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
void *_lsearch_s(
   const void *key,
   void *base,
   unsigned int *num,
   size_t size,
   int (__cdecl *compare)(void *, const void *, const void *),
   void * context
);
```

### <a name="parameters"></a>Parameter

*key*<br/>
Das Objekt, nach dem gesucht werden soll.

*base*<br/>
Zeiger auf der Basis des zu durchsuchenden Arrays.

*Anzahl*<br/>
Anzahl der Elemente.

*size*<br/>
Die Größe jedes Array-Elements in Bytes.

*compare*<br/>
Ein Zeiger auf die Vergleichsroutine. Der zweite Parameter ist ein Zeiger auf den Schlüssel für die Suche. Der dritte Parameter ist ein Zeiger auf das Arrayelement, das mit dem Schlüssel verglichen werden soll.

*context*<br/>
Ein Zeiger auf ein Objekt, auf das in der Vergleichsfunktion zugegriffen werden kann.

## <a name="return-value"></a>Rückgabewert

Wenn *Schlüssel* gefunden wird, **_lsearch_s** gibt einen Zeiger auf das Element des Arrays bei *Basis* entspricht *Schlüssel*. Wenn *Schlüssel* wurde nicht gefunden, **_lsearch_s** gibt einen Zeiger auf das neu hinzugefügte Element am Ende des Arrays.

Wenn ungültige Parameter an die Funktion übergeben werden, ruft sie den Handler für ungültige Parameter auf, wie in [Parameter Validation (Parametervalidierung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, klicken Sie dann **Errno** festgelegt ist, um **EINVAL** und die Funktion gibt **NULL**. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Fehlerbedingungen

|*key*|*base*|*compare*|*Anzahl*|*size*|**errno**|
|-----------|------------|---------------|-----------|------------|-------------|
|**NULL**|alle|alle|alle|alle|**EINVAL**|
|alle|**NULL**|alle|!= 0|alle|**EINVAL**|
|alle|alle|alle|alle|Null|**EINVAL**|
|alle|alle|**NULL**|ein|alle|**EINVAL**|

## <a name="remarks"></a>Hinweise

Die **_lsearch_s** Funktion führt eine lineare Suche für den Wert *Schlüssel* in ein Array von *Anzahl* Elementen, von denen jedes *Breite* Bytes. Im Gegensatz zu **Bsearch_s**, **_lsearch_s** erfordert nicht das Array, das sortiert werden. Wenn *Schlüssel* nicht gefunden wird, klicken Sie dann **_lsearch_s** fügt es am Ende des Arrays und Schritten *Anzahl*.

Die *vergleichen* Funktion ist ein Zeiger auf eine vom Benutzer bereitgestellte Routine, die zwei Arrayelemente vergleicht und einen Wert, der Angabe ihrer Beziehung zurückgibt. Die *vergleichen* Funktion nimmt auch den Zeiger auf den Kontext als erstes Argument. **_lsearch_s** Aufrufe *vergleichen* ein- oder mehrmals während der Suche, die Übergabe von Zeigern auf zwei Arrayelemente bei jedem Aufruf. *Vergleichen Sie* vergleichen Sie die Elemente und dann zurückgeben muss ungleich Null (d. h., die Elemente sind unterschiedlich) oder 0 (d. h., die Elemente sind identisch).

Die *Kontext* Zeiger kann nützlich sein, wenn die durchsuchte Datenstruktur Teil eines Objekts ist und die *vergleichen* Funktion benötigt, um auf Member des Objekts zuzugreifen. Code wird beispielsweise der *vergleichen* Funktion kann den void-Zeiger umgewandelt, in das entsprechende Objekt und auf Member des Objekts. Das Hinzufügen der *Kontext* Zeiger macht **_lsearch_s** sicherer, da weiterer Kontext verwendet werden kann, um Reentranz-Fehlern, die mit der Verwendung von statischer Variablen Daten zur Verfügung stellen zu vermeiden der *vergleichen* Funktion.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_lsearch_s**|\<search.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Suchen und Sortieren](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lfind_s](lfind-s.md)<br/>
[_lsearch](lsearch.md)<br/>
