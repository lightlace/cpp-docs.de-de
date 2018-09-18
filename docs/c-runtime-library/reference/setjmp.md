---
title: setjmp | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/14/2018
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
ms.openlocfilehash: 0bd7d57d0678744243356a0565e10cbe4065f8d3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032530"
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

Gibt 0 zurück, wenn die Stapelumgebung gespeichert wurde. Wenn **Setjmp** gibt als Ergebnis des eine `longjmp` aufrufen, gibt die *Wert* Argument `longjmp`, oder, wenn die *Wert* Argument `longjmp` ist 0 (null) **Setjmp** gibt 1 zurück. Es gibt keine Fehlerrückgabe.

## <a name="remarks"></a>Hinweise

Die **Setjmp** Funktion speichert eine stapelumgebung, die Sie später beim wiederherstellen können, `longjmp`. Bei Verwendung zusammen **Setjmp** und `longjmp` bieten eine Möglichkeit zum Ausführen eines nicht lokalen **Goto**. Sie werden in der Regel verwendet, um die Ausführungssteuerung an den Fehlerbehandlungs- oder Wiederherstellungscode in einer vorher aufgerufenen Routine zu übergeben, ohne die normalen Aufruf- oder Rückgabekonventionen zu verwenden.

Ein Aufruf von **Setjmp** speichert die aktuelle stapelumgebung in *Env*. Ein nachfolgender Aufruf von `longjmp` stellt die gespeicherte Umgebung wieder her und übergibt die Steuerung an den Punkt direkt nach dem entsprechenden **Setjmp** aufrufen. Alle Variablen (mit Ausnahme der Variablen „register“), die für die für das Steuerelement zur Routineerfassung zugänglich sind, erhalten die ursprünglichen Werte des `longjmp`-Aufrufs.

Es ist nicht möglich, verwenden Sie **Setjmp** von nativem zu verwaltetem Code zu springen.

**Microsoft-spezifisch**

In Microsoft C++-Code in Windows **Longjmp** verwendet dieselbe stapelentladung Semantik als Code zur Ausnahmebehandlung. Es ist sicher in denselben Situationen verwendet werden, dass die C++-Ausnahmen ausgelöst werden können. Jedoch diese Syntax ist nicht übertragbar und ist mit einigen wichtigsten Einschränkungen. Weitere Informationen finden Sie unter [Longjmp](longjmp.md).

**Ende Microsoft-spezifisch**

> [!NOTE]
> In der portablen C++-Code kann nicht davon ausgehen `setjmp` und `longjmp` C++-Objektsemantik unterstützt. Insbesondere eine `setjmp` / `longjmp` Aufruf Paar hat ein undefiniertes Verhalten ersetzen die `setjmp` und `longjmp` von **catch** und **auslösen** aufrufen würde Jede nicht triviale Destruktoren für automatische Objekte. In C++-Programme wird empfohlen, dass Sie den C++-Ausnahmebehandlung-Mechanismus verwenden.

Weitere Informationen finden Sie unter [Verwenden von „setjmp/longjmp“](../../cpp/using-setjmp-longjmp.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**setjmp**|\<setjmp.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel für [_fpreset](fpreset.md).

## <a name="see-also"></a>Siehe auch

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[longjmp](longjmp.md)
