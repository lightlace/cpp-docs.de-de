---
title: longjmp
ms.date: 08/14/2018
api_name:
- longjmp
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
- longjmp
helpviewer_keywords:
- restoring stack environment and execution locale
- longjmp function
ms.assetid: 0e13670a-5130-45c1-ad69-6862505b7a2f
ms.openlocfilehash: b4527a29475f9e393dc5abf19b866d926bec2ccc
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70953143"
---
# <a name="longjmp"></a>longjmp

Stellt die von einem `setjmp` -Befehl festgelegte Stapel Umgebung und das Ausführungs Gebiets Schema wieder her.

## <a name="syntax"></a>Syntax

```C
void longjmp(
   jmp_buf env,
   int value
);
```

### <a name="parameters"></a>Parameter

*env*<br/>
Variable, in der die Umgebung gespeichert wird.

*value*<br/>
Der Wert, der dem Aufruf `setjmp` zurückgegeben wird.

## <a name="remarks"></a>Hinweise

Die **longjmp** -Funktion stellt eine Stapel Umgebung und ein Ausführungs Gebiets Schema wieder her, `setjmp`die zuvor in *env* von gespeichert wurden. `setjmp`und **longjmp** bieten eine Möglichkeit, ein nicht lokales **goto**auszuführen. Sie werden normalerweise verwendet, um die Ausführungs Steuerung an den Fehler Behandlungs-oder Wiederherstellungscode in einer vorher aufgerufenen Routine zu übergeben, ohne die normalen Aufruf-und Rückgabe Konventionen zu verwenden.

Ein-Befehl bewirkt,dassdieaktuelleStapelUmgebunginder-Dateigespeichert`setjmp` wird. Ein nachfolgender Befehl von **longjmp** stellt die gespeicherte Umgebung wieder her und gibt die Steuerung an den Punkt `setjmp` zurück, der direkt auf den entsprechenden-Befehl folgt. Die Ausführung wird fortgesetzt, als ob der *Wert* gerade vom `setjmp`-Aufruf zurückgegeben worden wäre. Die Werte aller Variablen (außer Register Variablen), die für die Routine empfangende Steuerelemente zugänglich sind, enthalten die Werte, die Sie beim Aufrufen von " **longjmp** " hatten. Die Werte der Registervariablen sind unvorhersehbar. Der Wert, der von `setjmp` zurückgegeben wird, muss ungleich null sein. Wenn der *Wert* als 0 übergeben wird, wird der Wert 1 in der tatsächlichen Rückgabe ersetzt.

**Microsoft-spezifisch**

In Microsoft C++ -Code unter Windows verwendet **longjmp** die gleiche Semantik für die Stapel Auflösung wie den Code zur Ausnahmebehandlung. Es ist sicher, an denselben Stellen zu verwenden, C++ in denen Ausnahmen ausgelöst werden können. Diese Verwendung ist jedoch nicht portabel und enthält einige wichtige Einschränkungen.

Ruft nur **longjmp** auf, bevor die Funktion `setjmp` , die aufgerufen hat, zurückgibt. andernfalls sind die Ergebnisse unvorhersehbar.

Beachten Sie die folgenden Einschränkungen bei der Verwendung von **longjmp**:

- Gehen Sie nicht davon aus, dass die Werte der Registervariablen unverändert bleiben. Die Werte der Register Variablen in der Routine, `setjmp` die aufrufen, können nach der Ausführung von **longjmp** nicht in den richtigen Werten wieder hergestellt werden.

- Verwenden Sie **longjmp** nicht, um die Steuerung aus einer Unterbrechungs Behandlungs Routine zu übertragen, es sei denn, die Unterbrechung wird durch eine Gleit Komma Ausnahme verursacht. In diesem Fall kann ein Programm über **longjmp** von einem Interrupt-Handler zurückgegeben werden, wenn das Gleit Komma-mathematische Paket zum ersten Mal durch Aufrufen von [_fpreset](fpreset.md)erneut initialisiert wird.

- Verwenden Sie **longjmp** nicht, um die Steuerung aus einer Rückruf Routine zu übertragen, die direkt oder indirekt durch Windows-Code aufgerufen wird.

- Wenn der Code mithilfe von **/EHS** oder **/EHsc** kompiliert wird und die Funktion, die den **longjmp** -aufrufsvorgang enthält, **noist** , können lokale Objekte in dieser Funktion während der Stapel Entladung nicht zerstört werden.

**Ende Microsoft-spezifisch**

> [!NOTE]
> In portablen C++ Code können Sie nicht `setjmp` davon `longjmp` ausgehen C++ , dass Objekt Semantik unterstützt wird. Ein Aufruf Paar `setjmp` hat insbesondere ein `longjmp` / nicht definiertes Verhalten, `setjmp` Wenn `longjmp` das Ersetzen von und durch **catch** und **throw** alle nicht trivialen debugtoren für alle automatischen Objekte aufrufen würde. In C++ den Programmen wird empfohlen, den Mechanismus C++ für die Ausnahmebehandlung zu verwenden.

Weitere Informationen finden Sie unter [Verwenden von „setjmp/longjmp“](../../cpp/using-setjmp-longjmp.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**longjmp**|\<setjmp.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel für [_fpreset](fpreset.md).

## <a name="see-also"></a>Siehe auch

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[setjmp](setjmp.md)
