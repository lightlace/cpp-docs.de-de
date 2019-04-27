---
title: fwide
ms.date: 11/04/2016
apiname:
- fwide
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
- fwide
helpviewer_keywords:
- fwide function
ms.assetid: a4641f5b-d74f-4946-95d5-53a64610d28d
ms.openlocfilehash: d992ebc527744beeb4ef14175e3f10646a77a064
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287615"
---
# <a name="fwide"></a>fwide

Nicht implementiert

## <a name="syntax"></a>Syntax

```C
int fwide(
   FILE *stream,
   int mode;
);
```

### <a name="parameters"></a>Parameter

*stream*<br/>
Zeiger auf **Datei** -Struktur (ignoriert).

*mode*<br/>
Die neue Breite des Streams: positiv für Breitzeichen, negativ für Bytes, null, um unverändert zu lassen. (Dieser Wert wird ignoriert.)

## <a name="return-value"></a>Rückgabewert

Diese Funktion ist derzeit nur gibt *Modus*.

## <a name="remarks"></a>Hinweise

Die aktuelle Version dieser Funktion stimmt nicht mit dem Standard überein.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**fwide**|\<wchar.h>|

Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).