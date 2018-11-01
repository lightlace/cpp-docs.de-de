---
title: offsetof-Makro
ms.date: 11/04/2016
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
apitype: DLLExport
f1_keywords:
- offsetof
helpviewer_keywords:
- structure members, offset
- offsetof macro
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
ms.openlocfilehash: a0f367dbe6fa2681a7d413304f32b5699b8f7cee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50458319"
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

*MemberName*<br/>
Der Name des Elements in der übergeordneten Datenstruktur, für das der Offset bestimmt werden soll.

## <a name="return-value"></a>Rückgabewert

**Offsetof** gibt den Offset in Bytes, des angegebenen Elements vom Anfang seiner übergeordneten Datenstruktur zurück. Ist für Bitfelder nicht definiert.

## <a name="remarks"></a>Hinweise

Die **"offsetof"** Makro gibt den Offset in Bytes der *MemberName* vom Anfang der Struktur von *StructName* als ein Wert vom Typ **Size_ t**. Sie können angeben, dass Typen mit den **Struktur** Schlüsselwort.

> [!NOTE]
> **Offsetof** ist keine Funktion und kann nicht mit einem C-Prototyp beschrieben werden.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**offsetof**|\<stddef.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
