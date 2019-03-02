---
title: longjmp
ms.date: 08/14/2018
apiname:
- longjmp
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- longjmp
helpviewer_keywords:
- restoring stack environment and execution locale
- longjmp function
ms.assetid: 0e13670a-5130-45c1-ad69-6862505b7a2f
ms.openlocfilehash: e5189ff7cb850acd9c9a1280f47fc9a1270f8b68
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "57211003"
---
# <a name="longjmp"></a>longjmp

Stellt den Stapel und des ausführungsgebietschemas festlegen, indem eine `setjmp` aufrufen.

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

Die **Longjmp** Funktion stellt einen Stapel und des ausführungsgebietschemas zuvor gespeicherten *Env* von `setjmp`. `setjmp` und **Longjmp** bieten eine Möglichkeit, die Ausführung eines nicht lokalen **Goto**; sie werden in der Regel verwendet, um die ausführungssteuerung an Fehlerbehandlungs- oder Wiederherstellungscode in einer vorher aufgerufenen Routine zu übergeben, ohne mit dem normalen Aufruf und Rückgabekonventionen.

Ein Aufruf von `setjmp` bewirkt, dass die aktuelle stapelumgebung gespeichert werden soll *Env*. Ein nachfolgender Aufruf von **Longjmp** stellt die gespeicherte Umgebung wieder her und übergibt die Steuerung an den Punkt sofort nach der entsprechenden `setjmp` aufrufen. Die Ausführung wird fortgesetzt, als ob der *Wert* gerade vom `setjmp`-Aufruf zurückgegeben worden wäre. Die Werte aller Variablen (mit Ausnahme der Variablen "register"), die für die Übergabe der Steuerung Routine zugänglich sind, enthalten die Werte, die ihnen zugewiesen, wenn waren **Longjmp** aufgerufen wurde. Die Werte der Registervariablen sind unvorhersehbar. Der Wert, der von `setjmp` zurückgegeben wird, muss ungleich null sein. Wenn der *Wert* als 0 übergeben wird, wird der Wert 1 in der tatsächlichen Rückgabe ersetzt.

**Microsoft-spezifisch**

In Microsoft C++-Code in Windows **Longjmp** verwendet dieselbe stapelentladung Semantik als Code zur Ausnahmebehandlung. Es ist sicher in denselben Situationen verwendet werden, dass die C++-Ausnahmen ausgelöst werden können. Jedoch diese Syntax ist nicht übertragbar und ist mit einigen wichtigsten Einschränkungen.

Rufen Sie nur **Longjmp** vor der Funktion, die aufgerufen `setjmp` zurückgegeben; andernfalls sind die Ergebnisse unvorhersehbar.

Beachten Sie die folgenden Einschränkungen bei Verwendung **Longjmp**:

- Gehen Sie nicht davon aus, dass die Werte der Registervariablen unverändert bleiben. Die Werte der Variablen "Register" in der aufrufenden Routine `setjmp` kann nicht wiederhergestellt werden, auf die richtigen Werte nach **Longjmp** ausgeführt wird.

- Verwenden Sie keine **Longjmp** auf das Steuerelement aus einer interruptbehandlungsroutine zu übertragen, es sei denn, der die Unterbrechung durch eine Gleitkommaausnahme verursacht wird. In diesem Fall kann ein Programm aus einem Interrupthandler über zurückgeben **Longjmp** , wenn es zuerst mathematischen gleitkommapaket durch den Aufruf initialisiert [_fpreset](fpreset.md).

- Verwenden Sie keine **Longjmp** zum Übertragen von Steuerelement über eine Rückrufroutine, die direkt oder indirekt von der Windows-Code aufgerufen.

- Wenn der Code kompiliert wird, mit **/EHs** oder **/EHsc** und die Funktion, die enthält die **Longjmp** Aufruf **"noexcept"** klicken Sie dann lokale Objekte darin, dass die Funktion während der stapelentladung nicht zerstört werden kann.

**Ende Microsoft-spezifisch**

> [!NOTE]
> In der portablen C++-Code kann nicht davon ausgehen `setjmp` und `longjmp` C++-Objektsemantik unterstützt. Insbesondere eine `setjmp` / `longjmp` Aufruf Paar hat ein undefiniertes Verhalten ersetzen die `setjmp` und `longjmp` von **catch** und **auslösen** aufrufen würde Jede nicht triviale Destruktoren für automatische Objekte. In C++-Programme wird empfohlen, dass Sie den C++-Ausnahmebehandlung-Mechanismus verwenden.

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
