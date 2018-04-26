---
title: fwide | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- fwide function
ms.assetid: a4641f5b-d74f-4946-95d5-53a64610d28d
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a055df312215b5ff424aff54cfee54e0568ab307
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
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

*Stream*<br/>
Zeiger auf **Datei** Struktur (ignoriert).

*mode*<br/>
Die neue Breite des Streams: positiv für Breitzeichen, negativ für Bytes, null, um unverändert zu lassen. (Dieser Wert wird ignoriert.)

## <a name="return-value"></a>Rückgabewert

Diese Funktion wird zurzeit nur gibt *Modus*.

## <a name="remarks"></a>Hinweise

Die aktuelle Version dieser Funktion stimmt nicht mit dem Standard überein.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**fwide**|\<wchar.h>|

Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).