---
title: longjmp | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
apitype: DLLExport
f1_keywords:
- longjmp
dev_langs:
- C++
helpviewer_keywords:
- restoring stack environment and execution locale
- longjmp function
ms.assetid: 0e13670a-5130-45c1-ad69-6862505b7a2f
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0a593c2dcdfe1731ee5c6438c7a330e7f4ea8740
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="longjmp"></a>longjmp

Stellt die Stapelumgebung und das Ausführungsgebietschema wieder her

## <a name="syntax"></a>Syntax

```C
void longjmp(
   jmp_buf env,
   int value
);
```

### <a name="parameters"></a>Parameter

*Env* Variable, in welcher Umgebung gespeichert wird.

*Wert* zu zurückzugebenden Werts **Setjmp** aufrufen.

## <a name="remarks"></a>Hinweise

Die **Longjmp** Funktion stellt einen zuvor gespeicherten im Stapel und des ausführungsgebietschemas *Env* von **Setjmp**. **Setjmp** und **Longjmp** bieten eine Möglichkeit zum Ausführen einer nichtlokale **Goto**; sie werden normalerweise verwendet, um die ausführungssteuerung an den Fehlerbehandlungs- oder Wiederherstellung Code in einer vorher aufgerufenen Routine ohne übergeben Mithilfe der normalen aufrufen und Rückgabekonventionen.

Ein Aufruf von **Setjmp** bewirkt, dass die aktuelle Stapel Umgebung gespeichert werden kann *Env*. Ein nachfolgender Aufruf von **Longjmp** stellt die gespeicherte Umgebung wieder her, und die Steuerung an den Punkt unmittelbar nach der entsprechenden zurückgegeben **Setjmp** aufrufen. Ausführung fortgesetzt wird als *Wert* war nur zurückgegebenes der **Setjmp** aufrufen. Die Werte aller Variablen (mit Ausnahme der Variablen registrieren zu können), die für die Übergabe der Steuerung Routine zugänglich sind, enthalten die Werte, die ihnen zugewiesen, wenn waren **Longjmp** aufgerufen wurde. Die Werte der Registervariablen sind unvorhersehbar. Der Rückgabewert von **Setjmp** nicht NULL sein darf. Wenn der *Wert* als 0 übergeben wird, wird der Wert 1 in der tatsächlichen Rückgabe ersetzt.

Rufen Sie **Longjmp** vor der Funktion, die aufgerufen **Setjmp** zurückgibt; andernfalls sind die Ergebnisse unvorhersehbar.

Beachten Sie die folgenden Einschränkungen, wenn Sie mit **Longjmp**:

- Gehen Sie nicht davon aus, dass die Werte der Registervariablen unverändert bleiben. Die Werte der registervariablen in der aufrufenden Routine **Setjmp** möglicherweise nicht wiederhergestellt werden, um die richtigen Werte nach **Longjmp** ausgeführt wird.

- Verwenden Sie keine **Longjmp** Steuerung aus eine Interrupt-Behandlungsroutine übertragen werden, es sei denn, das die Unterbrechung durch eine Gleitkommaausnahme verursacht wird. In diesem Fall ein Programm über ein nicht maskierbarer Interrupt über gelegten **Longjmp** Wenn es mathematischen gleitkommapaket zunächst durch Aufrufen erneut initialisiert **_fpreset**.

     **Hinweis** werden mit Vorsicht **Setjmp** und **Longjmp** in C ++ ‑Programme. Da diese Funktionen keine C++-Objektsemantik unterstützt, ist es sicherer, den C++-Mechanismus zur Behandlung von Ausnahmen zu verwenden.

Weitere Informationen finden Sie unter [Verwenden von „setjmp/longjmp“](../../cpp/using-setjmp-longjmp.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**longjmp**|\<setjmp.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel für [_fpreset](fpreset.md).

## <a name="see-also"></a>Siehe auch

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[setjmp](setjmp.md)<br/>
