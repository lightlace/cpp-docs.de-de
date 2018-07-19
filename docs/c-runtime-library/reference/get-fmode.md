---
title: _get_fmode | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _get_fmode
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
- get_fmode
- _get_fmode
dev_langs:
- C++
helpviewer_keywords:
- _get_fmode function
- file translation [C++], default mode
- get_fmode function
ms.assetid: 22ea70e2-b9b5-422d-b514-64f4beaea45c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a28909e5e848712305fb28e8ac4d46180f8948cf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32398301"
---
# <a name="getfmode"></a>_get_fmode

Ruft den Standarddateiübersetzungsmodus für Datei E/A-Vorgänge auf.

## <a name="syntax"></a>Syntax

```C
errno_t _get_fmode( 
   int * pmode 
);
```

### <a name="parameters"></a>Parameter

*pmode*<br/>
Ein Zeiger auf eine ganze Zahl mit der aktuellen Standardmodus gefüllt werden soll: **_O_TEXT** oder **_O_BINARY**.

## <a name="return-value"></a>Rückgabewert

Gibt 0 (null) zurück, wenn der Vorgang erfolgreich war. Wenn ein Fehler auftritt, erscheint ein Fehlercode. Wenn *Pmode* ist **NULL**, den Handler für ungültige Parameter aufgerufen wird, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** festgelegt ist, um **EINVAL** und die Funktion gibt **EINVAL**.

## <a name="remarks"></a>Hinweise

Die Funktion legt die globale Variable [_fmode](../../c-runtime-library/fmode.md) fest. Diese Variable gibt den Standard-dateiübersetzungsmodus für beide auf niedriger Ebene und Datei-e/a-Vorgänge, wie z. B. streamen **_open**, **_pipe**, **Fopen**, und [ Freopen](freopen-wfreopen.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_get_fmode**|\<stdlib.h>|\<fcntl.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel in [_set_fmode](set-fmode.md).

## <a name="see-also"></a>Siehe auch

[_fmode](../../c-runtime-library/fmode.md)<br/>
[_set_fmode](set-fmode.md)<br/>
[_setmode](setmode.md)<br/>
[Text- und Binärmodusdatei-E/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md)<br/>
