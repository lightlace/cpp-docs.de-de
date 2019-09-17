---
title: _setjmp3
ms.date: 11/04/2016
api_name:
- _setjmp3
api_location:
- msvcrt.dll
- msvcr90.dll
- msvcr110.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- setjmp3
- _setjmp3
helpviewer_keywords:
- _setjmp3 function
- setjmp3 function
ms.assetid: 6129c2f3-8bac-4fdb-a827-44e1eebba500
ms.openlocfilehash: d7120ddd10322d0b7391608fd388d9f45c1600e8
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957786"
---
# <a name="_setjmp3"></a>_setjmp3

Interne CRT-Funktion. Eine neue Implementierung der Funktion `setjmp`.

## <a name="syntax"></a>Syntax

```
int _setjmp3(
   OUT jmp_buf env,
   int count,
   (optional parameters)
);
```

#### <a name="parameters"></a>Parameter

*env*<br/>
[out]: Adresse des Puffers zum Speichern von Statusinformationen.

*count*<br/>
[in]: Die Anzahl zusätzlicher `DWORD`s von Informationen, die in den `optional parameters` gespeichert werden.

*optional parameters*<br/>
[in]: Zusätzliche vom systeminternen Objekt `setjmp` gepushte Daten. Das erste `DWORD` ist ein Funktionszeiger, der verwendet wird, um zusätzliche Daten aufzurufen und zu einem nichtflüchtigen Speicherstatus zurückzukehren. Das zweite `DWORD` ist die wiederherzustellende Versuchsebene. Alle weiteren Daten werden im generischen Datenarray im `jmp_buf` gespeichert.

## <a name="return-value"></a>Rückgabewert

Gibt immer 0 zurück.

## <a name="remarks"></a>Anmerkungen

Verwenden Sie diese Funktion nicht in einem C++-Programm. Es handelt sich um eine intrinsische Funktion, die C++ nicht unterstützt. Weitere Informationen zum Verwenden von `setjmp` finden Sie unter [Verwenden von „setjmp/longjmp“](../cpp/using-setjmp-longjmp.md).

## <a name="requirements"></a>Requirements (Anforderungen)

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[setjmp](../c-runtime-library/reference/setjmp.md)
