---
title: _pclose
ms.date: 11/04/2016
api_name:
- _pclose
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
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _pclose
- pclose
helpviewer_keywords:
- _pclose function
- pclose function
- pipes, closing
ms.assetid: e2e31a9e-ba3a-4124-bcbb-c4040110b3d3
ms.openlocfilehash: 383dd96553463a2619537cf06fc6534770ed88d5
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951084"
---
# <a name="_pclose"></a>_pclose

Wartet auf einen neuen Befehlsprozessor und schließt den Stream auf der zugeordneten Pipe.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int _pclose(
FILE *stream
);
```

### <a name="parameters"></a>Parameter

*stream*<br/>
Rückgabewert des vorherigen Aufrufes **_popen**.

## <a name="return-value"></a>Rückgabewert

Gibt den Beendigungs Status des beendenden Befehls Prozessors zurück, oder-1, wenn ein Fehler auftritt. Das Format des Rückgabewerts ist mit dem Wert für **_cwait**identisch, mit dem Unterschied, dass die nieder wertigen und höherwertigen Bytes vertauscht werden. Wenn der Stream **null**ist, legt **_pclose** **errno** auf **EINVAL** fest und gibt-1 zurück.

Weitere Informationen über diese und andere Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_pclose** -Funktion sucht die Prozess-ID des Befehls Prozessors (cmd. exe), die vom zugeordneten **_popen** -Befehl gestartet wurde, führt einen [_cwait](cwait.md) -Befehl für den neuen Befehlsprozessor aus und schließt den Stream auf der zugeordneten Pipe.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_pclose**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[_pipe](pipe.md)<br/>
[_popen, _wpopen](popen-wpopen.md)<br/>
