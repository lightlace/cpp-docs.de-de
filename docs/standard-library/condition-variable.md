---
title: '&lt;condition_variable&gt;'
ms.date: 11/04/2016
f1_keywords:
- <condition_variable>
ms.assetid: 8567f7cc-20bd-42a7-9137-87c46f878009
ms.openlocfilehash: 3ce9125a13f0dd2f2e4f98a217c4373f2be2f8a8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663946"
---
# <a name="ltconditionvariablegt"></a>&lt;condition_variable&gt;

Definiert die Klassen [condition_variable](../standard-library/condition-variable-class.md) und [condition_variable_any](../standard-library/condition-variable-any-class.md), mit denen die Objekte erstellt werden, die auf das Eintreten einer Bedingung warten.

Für diesen Header wird "Concurrency Runtime (ConcRT)" verwendet, sodass er zusammen mit anderen ConcRT-Mechanismen verwendet werden kann. Weitere Informationen finden Sie unter [Concurrency Runtime](../parallel/concrt/concurrency-runtime.md).

## <a name="syntax"></a>Syntax

```cpp
#include <condition_variable>
```

> [!NOTE]
> Im Code, der kompiliert wird **"/ CLR"**, dieser Header blockiert.

### <a name="remarks"></a>Hinweise

Code, der auf eine Bedingungsvariable wartet, muss auch einen `mutex` verwenden. Ein aufrufender Thread muss den `mutex` vor dem Aufrufen der Funktionen, die auf die Bedingungsvariable warten, sperren. Der `mutex` ist dann gesperrt, wenn die aufgerufene Funktion zurückgegeben wird. Die `mutex` ist nicht gesperrt, während der Thread auf das Eintreten der Bedingung wartet. Damit keine unvorhersehbaren Ergebnisse produziert werden, muss jeder Thread, der auf eine Bedingungsvariable wartet, das gleiche `mutex` Objekt verwenden.

Objekte vom Typ `condition_variable_any` können mit einem Mutex eines beliebigen Typs verwendet werden. Der Typ des verwendeten Mutex muss keine `try_lock`-Methode angeben. Objekte vom Typ `condition_variable` können ausschließlich mit einem Mutex des Typs `unique_lock<mutex>` verwendet werden. Objekte dieses Typs sind möglicherweise schneller als Objekte vom Typ `condition_variable_any<unique_lock<mutex>>`.

Sie warten auf ein Ereignis, indem Sie zuerst den Mutex sperren und anschließend eine der `wait`-Methoden auf der Bedingungsvariablen aufrufen. Der `wait`-Aufruf wird so lange gesperrt, bis ein anderer Thread die Bedingungsvariable signalisiert.

*Spurious Wakeups* treten auf, wenn die Threads, die auf die Bedingungsvariable warten, ohne geeignete Benachrichtigungen entsperrt werden. Ein solches fälschliches Aufwecken kann durch den Code, der auf das Eintreten der Bedingung wartet, erkannt werden. Dazu muss er jedoch prüfen, ob die Bedingung, auf die er wartet, tatsächlich eingetreten ist. Dies erfolgt in der Regel mithilfe einer Schleife. Verwenden Sie `wait(unique_lock<mutex>& lock, Predicate pred)`, um diese Schleife für Sie durchzuführen.

```cpp
while (condition is false)
    wait for condition variable;
```

Die `condition_variable_any`- und `condition_variable`- Klassen verfügen über drei Methoden, um auf eine Bedingung zu warten.

- `wait` wartet für einen unbegrenzten Zeitraum.

- `wait_until` wartet, bis einem angegebenen Zeitpunkt (`time`).

- `wait_for` wartet, bis zu einer angegebenen Dauer (`time interval`).

Jede dieser Methoden verfügt über zwei überladene Versionen. Eine davon wartet einfach und kann fälschlicherweise aufwachen. Die andere verwendet ein zusätzliches Vorlagenargument, das ein Prädikat definiert. Die Methode wird nicht zurückgegeben werden, bis das Prädikat **"true"**.

Jede Klasse verfügt auch über zwei Methoden, mit denen eine Bedingungsvariable benachrichtigt wird, die die Bedingung den Wert **"true"**.

- `notify_one` weckt einen der Threads auf, der auf die Bedingungsvariable wartet.

- `notify_all` weckt alle Threads auf, die auf die Bedingungsvariable warten.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[condition_variable-Klasse](../standard-library/condition-variable-class.md)<br/>
[condition_variable_any-Klasse](../standard-library/condition-variable-any-class.md)<br/>
