---
title: __security_init_cookie
ms.date: 11/04/2016
api_name:
- __security_init_cookie
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
- security_init_cookie
- __security_init_cookie
helpviewer_keywords:
- security cookie [C++]
- __security_init_cookie function
- security_init_cookie function
- global security cookie
ms.assetid: 32119905-0897-4a1c-84ca-bffd16c9b2af
ms.openlocfilehash: 9f7e9924f4a96803749418d777e5ee2020f9df78
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948716"
---
# <a name="__security_init_cookie"></a>__security_init_cookie

Initialisiert das globale Sicherheitscookie.

## <a name="syntax"></a>Syntax

```C
void __security_init_cookie(void);
```

## <a name="remarks"></a>Hinweise

Das globale Sicherheitscookie wird zum Schutz vor Pufferüberlauf in dem Code verwendet, der mit [/GS (Puffer-Sicherheitsüberprüfung)](../../build/reference/gs-buffer-security-check.md) kompiliert wurde, sowie in Code mit Ausnahmebehandlung. Beim Einstieg in eine vor Pufferüberlauf geschützte Funktion wird das Cookie auf dem Stapel abgelegt, und bei Funktionsende wird der Wert auf dem Stapel mit dem globalen Cookie verglichen. Jeglicher Unterschied zwischen diesen Werten weist darauf hin, dass ein Pufferüberlauf eingetreten ist. Das Programm wird daraufhin sofort beendet.

Normalerweise wird **__security_init_cookie** von der CRT aufgerufen, wenn Sie initialisiert wird. Wenn Sie die CRT-Initialisierung umgehen – Wenn Sie z. b. [/Entry](../../build/reference/entry-entry-point-symbol.md) verwenden, um einen Einstiegspunkt anzugeben –, müssen Sie **__security_init_cookie** selbst abrufen. Wenn **__security_init_cookie** nicht aufgerufen wird, wird das globale Sicherheits Cookie auf einen Standardwert festgelegt, und der Schutz vor Pufferüberlauf ist gefährdet. Da ein Angreifer diesen Standardwert für den Cookie ausnutzen kann, um die Pufferüberlauf Prüfungen zu besiegen, empfiehlt es sich, immer **__security_init_cookie** aufzurufen, wenn Sie einen eigenen Einstiegspunkt definieren.

Der **__security_init_cookie** -Aufrufe muss erfolgen, bevor eine Überlauf geschützte Funktion eingegeben wird. Andernfalls wird ein falscher Pufferüberlauf erkannt. Weitere Informationen finden Sie unter [C-Laufzeitfehler R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md).

## <a name="example"></a>Beispiel

Beispiele finden Sie unter [C-Laufzeitfehler R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**__security_init_cookie**|\<process.h>|

**__security_init_cookie** ist eine Microsoft-Erweiterung der Standard-C-Lauf Zeit Bibliothek. Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Microsoft Security Response Center](https://www.microsoft.com/msrc?rtc=1)
