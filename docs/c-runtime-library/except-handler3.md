---
title: _except_handler3 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
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
dev_langs:
- C++
helpviewer_keywords:
- _except_handler3 function
- except_handler3 function
ms.assetid: b0c64898-0ae5-48b7-9724-80135a0813e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b1b93cf52ee7690aa86f4a80acae2731197ec9d9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115371"
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