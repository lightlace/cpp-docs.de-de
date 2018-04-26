---
title: _set_abort_behavior | Microsoft-Dokumentation
ms.custom: ''
ms.date: 1/02/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _set_abort_behavior
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
- _set_abort_behavior
- set_abort_behavior
dev_langs:
- C++
helpviewer_keywords:
- aborting programs
- _set_abort_behavior function
- set_abort_behavior function
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b7ee65b603997a0be4fe9e937299eab9520c6f5b
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="setabortbehavior"></a>_set_abort_behavior

Gibt die Aktion an, die ausgeführt werden soll, wenn ein Programm nicht normal beendet wird.

> [!NOTE]
> Verwenden Sie nicht die [abort](abort.md) Funktion, um eine Microsoft Store-app mit Ausnahme von Herunterfahren in Test- oder Debugszenarien. Programmgesteuerte oder UI-Methoden zum Schließen einer Store-app sind nicht zulässig, gemäß der [Microsoft Store-Richtlinien](http://go.microsoft.com/fwlink/?LinkId=865936). Weitere Informationen finden Sie unter [uwp-app-Lebenszyklus](http://go.microsoft.com/fwlink/p/?LinkId=865934).

## <a name="syntax"></a>Syntax

```C
unsigned int _set_abort_behavior(
   unsigned int flags,
   unsigned int mask
);
```

### <a name="parameters"></a>Parameter

*flags*<br/>
Der neue Wert der [abort](abort.md) Flags.

*Maske*<br/>
Maske für die [abort](abort.md) kennzeichnet festzulegenden Bits.

## <a name="return-value"></a>Rückgabewert

Der alte Wert der Flags.

## <a name="remarks"></a>Hinweise

Es gibt zwei [abort](abort.md) Flags: **_WRITE_ABORT_MSG** und **_CALL_REPORTFAULT**. **_WRITE_ABORT_MSG** bestimmt, ob eine informative textmeldung gedruckt wird, wenn ein Programm nicht normal beendet wird. Die Meldung besagt, dass die Anwendung aufgerufen hat die [abort](abort.md) Funktion. Beim Standardverhalten wird die Meldung ausgeben. **_CALL_REPORTFAULT**, sofern festgelegt, gibt an, dass ein Watson-Absturzabbild generiert und, wenn gemeldet [abort](abort.md) aufgerufen wird. Standardmäßig ist die Absturzabbildberichterstellung in den Nichtdebugversionen aktiviert.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_set_abort_behavior**|\<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_set_abort_behavior.c
// compile with: /TC
#include <stdlib.h>

int main()
{
   printf("Suppressing the abort message. If successful, this message"
          " will be the only output.\n");
   // Suppress the abort message
   _set_abort_behavior( 0, _WRITE_ABORT_MSG);
   abort();
}
```

```Output
Suppressing the abort message. If successful, this message will be the only output.
```

## <a name="see-also"></a>Siehe auch

[abort](abort.md)<br/>
