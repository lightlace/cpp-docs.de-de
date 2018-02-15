---
title: _open_osfhandle | Microsoft-Dokumentation
ms.custom: 
ms.date: 12/12/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 34f60a327f3bc4c6a6ce1beb6d7b399faa393a70
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
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

*osfhandle*  
Betriebssystem-Dateihandle.

*flags*  
Zulässige Vorgangsarten.

## <a name="return-value"></a>Rückgabewert

Im Erfolgsfall gibt `_open_osfhandle` einen C-Laufzeit-Dateideskriptor zurück. Andernfalls wird-1 zurückgegeben.

## <a name="remarks"></a>Hinweise

Die `_open_osfhandle` Funktion weist einen C-Laufzeit-Dateideskriptor und ordnet das Betriebssystem-Dateihandle gemäß *Osfhandle*. Die *Flags* Argument ist ein Ganzzahlausdruck, der aus einer oder mehreren der in Fcntl.h definierten Manifestkonstanten gebildet. Wenn zwei oder mehr Manifestkonstanten verwendet werden, in Form der *Flags* Argument, werden die Konstanten mit dem bitweisen OR-Operator kombiniert ( **&#124;** ).

Fcntl.h definiert die folgenden Manifestkonstanten besteht:

**\_O\_ANFÜGEN**  
Positioniert einen Dateizeiger vor jedem Schreibvorgang am Ende der Datei.

**\_O\_RDONLY**  
Öffnet eine Datei nur zum Lesen.

**\_O\_TEXT**  
Öffnet eine Datei im Textmodus (übersetzt).

**\_O\_WTEXT**  
Öffnet eine Datei in Unicode (übersetzt UTF-16).

Schließen eine geöffnete Datei `_open_osfhandle`, rufen Sie [ \_schließen](../../c-runtime-library/reference/close.md). Das zugrunde liegende Betriebssystem-Dateihandle ist ebenfalls geschlossen, durch den Aufruf von `_close`, daher ist es nicht notwendig, die Win32-Funktion `CloseHandle` auf das ursprüngliche Handle. Wenn der Dateideskriptor Besitz ist ein `FILE *` Stream und anschließend durch Aufrufen [Fclose](../../c-runtime-library/reference/fclose-fcloseall.md) darauf `FILE *` Stream schließt auch den Dateideskriptor und das zugrunde liegende Handle. Rufen Sie in diesem Fall nicht `_close` auf den Dateideskriptor.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|`_open_osfhandle`|\<io.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)  
