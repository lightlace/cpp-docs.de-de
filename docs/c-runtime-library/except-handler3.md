---
title: _except_handler3
ms.date: 11/04/2016
apiname:
- _except_handler3
apilocation:
- msvcrt.dll
- msvcr90.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- _except_handler3
- except_handler3
helpviewer_keywords:
- _except_handler3 function
- except_handler3 function
ms.assetid: b0c64898-0ae5-48b7-9724-80135a0813e2
ms.openlocfilehash: 144bf25495d803a4db42ab45fcb0b101b09fe7cc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613862"
---
# <a name="excepthandler3"></a>_except_handler3

Interne CRT-Funktion. Wird von einem Framework verwendet, um den passenden Ausnahmehandler zur Verarbeitung der aktuellen Ausnahme zu suchen.

## <a name="syntax"></a>Syntax

```
int _except_handler3(
   PEXCEPTION_RECORD exception_record,
   PEXCEPTION_REGISTRATION registration,
   PCONTEXT context,
   PEXCEPTION_REGISTRATION dispatcher
);
```

#### <a name="parameters"></a>Parameter

*exception_record*<br/>
[in]: Informationen über die spezifische Ausnahme.

*registration*<br/>
[in]: Der Datensatz, der angibt, welche Bereichstabelle für die Suche nach dem Ausnahmehandler verwendet werden soll.

*context*<br/>
[in]: Reserviert

*dispatcher*<br/>
[in]: Reserviert

## <a name="return-value"></a>Rückgabewert

Gibt `DISPOSITION_DISMISS` zurück, wenn eine Ausnahme verworfen wird. Gibt `DISPOSITION_CONTINUE_SEARCH` zurück, wenn die Ausnahme eine Ebene höher an die kapselnden Ausnahmehandler übergeben wird.

## <a name="remarks"></a>Hinweise

Wenn diese Methode einen passenden Ausnahmehandler findet, übergibt sie die Ausnahme an diesen Handler. In dieser Situation wird diese Methode nicht an den Code zurückgegeben, der sie aufgerufen hat, und der Rückgabewert ist irrelevant.

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](../c-runtime-library/reference/crt-alphabetical-function-reference.md)