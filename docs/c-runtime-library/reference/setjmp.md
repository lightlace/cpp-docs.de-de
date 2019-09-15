---
title: setjmp
ms.date: 08/14/2018
api_name:
- setjmp
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
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- setjmp
helpviewer_keywords:
- programs [C++], saving states
- current state
- setjmp function
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
ms.openlocfilehash: 4a88467f5b94ceae4281a35f1486380a877be2e5
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948239"
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

Gibt 0 zurück, wenn die Stapelumgebung gespeichert wurde. Wenn **setjmp** als Ergebnis eines `longjmp` -Aufrufes zurückgibt, gibt es das Wert `longjmp`Argument von zurück, oder wenn das `longjmp` Wert Argument von 0 ist, gibt **setjmp** den *Wert* 1 zurück. Es gibt keine Fehlerrückgabe.

## <a name="remarks"></a>Hinweise

Die **setjmp** -Funktion speichert eine Stapel Umgebung, die Sie anschließend mithilfe `longjmp`von wiederherstellen können. Bei der gemeinsamen Verwendung von **setjmp** und `longjmp` bieten eine Möglichkeit, ein nicht lokales **goto**auszuführen. Sie werden in der Regel verwendet, um die Ausführungssteuerung an den Fehlerbehandlungs- oder Wiederherstellungscode in einer vorher aufgerufenen Routine zu übergeben, ohne die normalen Aufruf- oder Rückgabekonventionen zu verwenden.

Ein Aufrufen von **setjmp** speichert die aktuelle Stapel *Umgebung in der*-Umgebung. Ein nachfolgendes aufrufen `longjmp` von stellt die gespeicherte Umgebung wieder her und gibt die Steuerung an den Punkt direkt nach dem entsprechenden **setjmp** -Befehl zurück. Alle Variablen (mit Ausnahme der Variablen „register“), die für die für das Steuerelement zur Routineerfassung zugänglich sind, erhalten die ursprünglichen Werte des `longjmp`-Aufrufs.

Es ist nicht möglich, **setjmp** zu verwenden, um von nativem zu verwaltetem Code zu springen.

**Microsoft-spezifisch**

In Microsoft C++ -Code unter Windows verwendet **longjmp** die gleiche Semantik für die Stapel Auflösung wie den Code zur Ausnahmebehandlung. Es ist sicher, an denselben Stellen zu verwenden, C++ in denen Ausnahmen ausgelöst werden können. Diese Verwendung ist jedoch nicht portabel und enthält einige wichtige Einschränkungen. Weitere Informationen finden Sie unter [longjmp](longjmp.md).

**Ende Microsoft-spezifisch**

> [!NOTE]
> In portablen C++ Code können Sie nicht `setjmp` davon `longjmp` ausgehen C++ , dass Objekt Semantik unterstützt wird. Ein Aufruf Paar `setjmp` hat insbesondere ein `longjmp` / nicht definiertes Verhalten, `setjmp` Wenn `longjmp` das Ersetzen von und durch **catch** und **throw** alle nicht trivialen debugtoren für alle automatischen Objekte aufrufen würde. In C++ den Programmen wird empfohlen, den Mechanismus C++ für die Ausnahmebehandlung zu verwenden.

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
