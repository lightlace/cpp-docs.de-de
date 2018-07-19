---
title: _set_errno | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _set_errno
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_errno
- _set_errno
dev_langs:
- C++
helpviewer_keywords:
- errno global variable
- set_errno function
- _set_errno function
ms.assetid: d338914a-1894-4cf3-ae45-f2c4eb26590b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 87c51aa82485b259a1911793d7aececf7534b144
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32406081"
---
# <a name="seterrno"></a>_set_errno

Legen Sie den Wert, der die **Errno** (globale Variable).

## <a name="syntax"></a>Syntax

```C
errno_t _set_errno( int error_value );
```

### <a name="parameters"></a>Parameter

*error_value*<br/>
Der neue Wert des **Errno**.

## <a name="return-value"></a>Rückgabewert

Gibt 0 zurück, wenn erfolgreich.

## <a name="remarks"></a>Hinweise

Mögliche Werte sind in Errno.h definiert. Siehe auch [errno-Konstanten](../../c-runtime-library/errno-constants.md).

## <a name="example"></a>Beispiel

```C
// crt_set_errno.c
#include <stdio.h>
#include <errno.h>

int main()
{
   _set_errno( EILSEQ );
   perror( "Oops" );
}
```

```Output
Oops: Illegal byte sequence
```

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_set_errno**|\<stdlib.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[_get_errno](get-errno.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
