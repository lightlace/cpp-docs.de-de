---
title: unexpected (CRT)
ms.date: 11/04/2016
api_name:
- unexpected
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
- unexpected
helpviewer_keywords:
- unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
ms.openlocfilehash: 796f5ddbf8467656b5430de1d504f162d891864d
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957822"
---
# <a name="unexpected-crt"></a>unexpected (CRT)

Aufrufe **Beenden** oder Funktion, die Sie mit **Set_unexpected**angeben.

## <a name="syntax"></a>Syntax

```C
void unexpected( void );
```

## <a name="remarks"></a>Hinweise

Die **unerwartete** Routine wird nicht mit der aktuellen Implementierung der C++ Ausnahmebehandlung verwendet. **unerwartete** Aufrufe werden standardmäßig **beendet** . Sie können dieses Standardverhalten ändern, indem Sie eine benutzerdefinierte Beendigungs Funktion schreiben und **Set_unexpected** mit dem Namen ihrer Funktion als Argument aufrufen. **unerwartete** Aufrufe der letzten Funktion, die als Argument für **Set_unexpected**angegeben wurde.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**unexpected**|\<eh.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlungsroutinen](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_set_se_translator](set-se-translator.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[terminate](terminate-crt.md)<br/>
