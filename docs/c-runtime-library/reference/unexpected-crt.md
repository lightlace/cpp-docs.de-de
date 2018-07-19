---
title: unexpected (CRT) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd8dc51c41ebf938f59493cbd62fac3e0a491601
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32408106"
---
# <a name="unexpected-crt"></a>unexpected (CRT)

Aufrufe **beenden** oder eine Funktion, die Sie angeben, mit **Set_unexpected**.

## <a name="syntax"></a>Syntax

```C
void unexpected( void );
```

## <a name="remarks"></a>Hinweise

Die **unerwarteter** Routine nicht mit der aktuellen Implementierung der C++-Ausnahmebehandlung verwendet wird. **Unerwarteter** Aufrufe **beenden** standardmäßig. Sie können dieses Standardverhalten ändern, indem Sie eine benutzerdefinierte Beendigungsfunktion schreiben und Aufrufen **Set_unexpected** mit dem Namen Ihrer Funktion als Argument. **Unerwarteter** Ruft die letzte Funktion als Argument an **Set_unexpected**.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
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
