---
title: _aligned_offset_malloc | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _aligned_offset_malloc
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _aligned_offset_malloc
- aligned_offset_malloc
dev_langs:
- C++
helpviewer_keywords:
- _aligned_offset_malloc function
- aligned_offset_malloc function
ms.assetid: 447681a3-7c95-4655-86ba-fa3a4ca4c521
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8bcc5fe0d786c7fdb04455f231cc3c8e60b53a22
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32392844"
---
# <a name="alignedoffsetmalloc"></a>_aligned_offset_malloc

Weist Speicher mit einer definierten Zuweisungsgrenze zu.

## <a name="syntax"></a>Syntax

```C
void * _aligned_offset_malloc(
   size_t size,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>Parameter

*size*<br/>
Die Größe der angeforderten Speicherbelegung.

*Ausrichtung*<br/>
Der Ausrichtungswert, der eine ganzzahlige Potenz von 2 sein muss.

*offset*<br/>
Der Offset in der Speicherbelegung zum Erzwingen der Ausrichtung.

## <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Speicherblock, der belegt wurde oder **NULL** bei fehlgeschlagenem Vorgang.

## <a name="remarks"></a>Hinweise

**_aligned_offset_malloc** eignet sich für Situationen, in denen eine Ausrichtung für ein geschachteltes Element; erforderlich ist z. B., wenn eine Ausrichtung für eine geschachtelte Klasse erforderlich war.

**_aligned_offset_malloc** basiert auf **"malloc"**; Weitere Informationen finden Sie unter ["malloc"](malloc.md).

**_aligned_offset_malloc** RuntimeCompatibility `__declspec(noalias)` und `__declspec(restrict)`, was bedeutet, dass die Funktion garantiert nicht, so ändern Sie globale Variablen und der zurückgegebene Zeiger keinen Alias. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md) und [restrict](../../cpp/restrict.md).

Diese Funktion legt **Errno** auf **ENOMEM** , wenn die speicherbelegung fehlgeschlagen ist oder wenn die angeforderte Größe größer war **_HEAP_MAXREQ**. Weitere Informationen zu **Errno**, finden Sie unter [Errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Darüber hinaus **_aligned_offset_malloc** überprüft die eigenen Parameter. Wenn *Ausrichtung* Potenz von 2 ist oder wenn *Offset* ist größer als oder gleich *Größe* und ungleich NULL ist, ruft diese Funktion den Handler für ungültige Parameter wie beschrieben in [ Überprüfen der Parameter](../../c-runtime-library/parameter-validation.md). Diese Funktion gibt zurück, wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **NULL** und legt **Errno** auf **EINVAL**.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_aligned_offset_malloc**|\<malloc.h>|

## <a name="example"></a>Beispiel

Weitere Informationen finden Sie unter [_aligned_malloc](aligned-malloc.md).

## <a name="see-also"></a>Siehe auch

[Datenausrichtung](../../c-runtime-library/data-alignment.md)<br/>
