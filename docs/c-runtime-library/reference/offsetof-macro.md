---
title: offsetof-Makro
ms.date: 11/04/2016
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- offsetof
helpviewer_keywords:
- structure members, offset
- offsetof macro
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
ms.openlocfilehash: 278fca89046fcfc98e8c3ff726918cb4319e4ab0
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951247"
---
# <a name="offsetof-macro"></a>offsetof-Makro

Ruft den Offset eines Elements vom Anfang seiner übergeordneten Struktur ab.

## <a name="syntax"></a>Syntax

```C
size_t offsetof(
   structName,
   memberName
);
```

### <a name="parameters"></a>Parameter

*structName*<br/>
Der Name der übergeordneten Datenstruktur.

*memberName*<br/>
Der Name des Elements in der übergeordneten Datenstruktur, für das der Offset bestimmt werden soll.

## <a name="return-value"></a>Rückgabewert

**offsetof** gibt den Offset des angegebenen Elements vom Anfang seiner übergeordneten Datenstruktur in Bytes zurück. Ist für Bitfelder nicht definiert.

## <a name="remarks"></a>Hinweise

Das **offsetof** -Makro gibt den Offset in Bytes des *Mitgliedsnamens* von dem Anfang der Struktur zurück, der von *structname* als Wert des Typs **size_t**angegeben wird. Sie können Typen mit dem **struct** -Schlüsselwort angeben.

> [!NOTE]
> **offsetof** ist keine Funktion und kann nicht mit einem C-Prototyp beschrieben werden.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**offsetof**|\<stddef.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
