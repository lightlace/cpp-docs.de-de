---
title: _open_osfhandle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/12/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _open_osfhandle
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _open_osfhandle
- open_osfhandle
dev_langs:
- C++
helpviewer_keywords:
- open_osfhandle function
- file handles [C++], associating
- _open_osfhandle function
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 270b17ce72ece85687c23678908e10bc1dcc3764
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="openosfhandle"></a>_open_osfhandle

Ordnet den C-Laufzeit-Dateideskriptor einem vorhandenen Betriebssystem-Dateihandle zu.

## <a name="syntax"></a>Syntax

```cpp
int _open_osfhandle (
   intptr_t osfhandle,
   int flags
);
```

### <a name="parameters"></a>Parameter

*osfhandle*<br/>
Betriebssystem-Dateihandle.

*flags*<br/>
Zulässige Vorgangsarten.

## <a name="return-value"></a>Rückgabewert

Im Erfolgsfall **_open_osfhandle** gibt einen C-Laufzeit-Dateideskriptor zurück. Andernfalls wird-1 zurückgegeben.

## <a name="remarks"></a>Hinweise

Die **_open_osfhandle** Funktion weist einen C-Laufzeit-Dateideskriptor und ordnet das Betriebssystem-Dateihandle gemäß *Osfhandle*. Die *Flags* Argument ist ein Ganzzahlausdruck, der aus einer oder mehreren der in Fcntl.h definierten Manifestkonstanten gebildet. Wenn zwei oder mehr Manifestkonstanten verwendet werden, in Form der *Flags* Argument, werden die Konstanten mit dem bitweisen OR-Operator kombiniert ( **&#124;** ).

Fcntl.h definiert die folgenden Manifestkonstanten besteht:

**\_O\_APPEND** positioniert einen Dateizeiger am Ende der Datei vor jedem Schreibvorgang.

**\_O\_RDONLY** öffnet die Datei nur zum Lesen.

**\_O\_TEXT** öffnet die Datei im Textmodus (übersetzt).

**\_O\_WTEXT** öffnet die Datei im Unicode (UTF-16 übersetzte) Modus.

Schließen eine geöffnete Datei **_open_osfhandle**, rufen Sie [ \_schließen](close.md). Das zugrunde liegende Betriebssystem-Dateihandle ist ebenfalls geschlossen, durch den Aufruf von **_close**, daher ist es nicht notwendig, die Win32-Funktion **CloseHandle** auf das ursprüngliche Handle. Wenn der Dateideskriptor Besitz ist ein **Datei &#42;**  Stream und anschließend durch Aufrufen [Fclose](fclose-fcloseall.md) auf, die **Datei &#42;**  Stream schließt außerdem sowohl den Dateideskriptor und die zugrunde liegende Handle. Rufen Sie in diesem Fall nicht **_close** auf den Dateideskriptor.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_open_osfhandle**|\<io.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
