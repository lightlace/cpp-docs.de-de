---
title: setjmp | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- setjmp
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
- setjmp
dev_langs:
- C++
helpviewer_keywords:
- programs [C++], saving states
- current state
- setjmp function
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2cc4673485577f5a12024d31e94063c82a8c7b8c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="setjmp"></a>setjmp

Speichert den aktuellen Zustand des Programms.

## <a name="syntax"></a>Syntax

```C
int setjmp(
   jmp_buf env
);
```

### <a name="parameters"></a>Parameter

*env*<br/>
Variable, in der die Umgebung gespeichert wird.

## <a name="return-value"></a>Rückgabewert

Gibt 0 zurück, wenn die Stapelumgebung gespeichert wurde. Wenn **Setjmp** gibt als Ergebnis des eine **Longjmp** aufrufen, gibt die **Wert** Argument **Longjmp**, oder wenn die **Wert**  Argument **Longjmp** ist 0, **Setjmp** gibt 1 zurück. Es gibt keine Fehlerrückgabe.

## <a name="remarks"></a>Hinweise

Die **Setjmp** Funktion speichert eine Stack-Umgebung, die Sie später beim wiederherstellen können, **Longjmp**. Bei Verwendung zusammen **Setjmp** und **Longjmp** bieten eine Möglichkeit zum Ausführen eines nicht lokalen **Goto**. Sie werden in der Regel verwendet, um die Ausführungssteuerung an den Fehlerbehandlungs- oder Wiederherstellungscode in einer vorher aufgerufenen Routine zu übergeben, ohne die normalen Aufruf- oder Rückgabekonventionen zu verwenden.

Ein Aufruf von **Setjmp** speichert den aktuellen Stapel-Umgebung in *Env*. Ein nachfolgender Aufruf von **Longjmp** stellt die gespeicherte Umgebung wieder her und die Steuerung zurückgegeben zu dem Punkt direkt hinter das entsprechende **Setjmp** aufrufen. Alle Variablen (mit Ausnahme von registervariablen) zugegriffen werden kann, um die Übergabe der Steuerung Routine enthalten die Werte, die ihnen zugewiesen, wenn waren **Longjmp** aufgerufen wurde.

Es ist nicht möglich, verwenden Sie **Setjmp** von systemeigenem Code zu verwaltetem Code zu springen.

**Hinweis** **Setjmp** und **Longjmp** unterstützen keine Semantik für C++-Objekt. Verwenden Sie den C++-Mechanismus für die Ausnahmebehandlung in C++-Programmen.

Weitere Informationen finden Sie unter [Verwenden von „setjmp/longjmp“](../../cpp/using-setjmp-longjmp.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**setjmp**|\<setjmp.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel für [_fpreset](fpreset.md).

## <a name="see-also"></a>Siehe auch

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[longjmp](longjmp.md)<br/>
[_setjmp3](../../c-runtime-library/setjmp3.md)<br/>
