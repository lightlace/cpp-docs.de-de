---
title: unexpected (CRT)
ms.date: 11/04/2016
apiname:
- unexpected
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
- unexpected
helpviewer_keywords:
- unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
ms.openlocfilehash: 78538c0a10e183e72c742b041b297275c0859a03
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534019"
---
# <a name="unexpected-crt"></a>unexpected (CRT)

Aufrufe **beenden** oder eine Funktion, die Sie angeben, mit **Set_unexpected**.

## <a name="syntax"></a>Syntax

```C
void unexpected( void );
```

## <a name="remarks"></a>Hinweise

Die **unerwartete** Routine ist nicht mit der aktuellen Implementierung von C++-Ausnahmebehandlung verwendet. **Unerwarteter** Aufrufe **beenden** standardmäßig. Sie können dieses Standardverhalten ändern, indem eine benutzerdefinierte Beendigungsfunktion schreiben und Aufrufen **Set_unexpected** mit dem Namen Ihrer Funktion als Argument. **Unerwarteter** Ruft die letzte Funktion, die als Argument an **Set_unexpected**.

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
