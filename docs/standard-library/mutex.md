---
title: '&lt;mutex&gt; | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <mutex>
dev_langs:
- C++
ms.assetid: efb60c89-687a-4e38-8fe4-694e11c4e8a3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9cd4f968543ff777b9178c8f6fa6b3c1699ee465
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965655"
---
# <a name="ltmutexgt"></a>&lt;mutex&gt;

Verwenden Sie den Standardheader \<mutex> für das Definieren der Klassen `mutex`, `recursive_mutex`, `timed_mutex` und `recursive_timed_mutex`, der Vorlagen `lock_guard` und `unique_lock` sowie der unterstützenden Typen und Funktionen, die Codebereiche für den gegenseitigen Ausschluss definieren.

> [!WARNING]
> Ab Visual Studio 2015, die Synchronisierungstypen der C++-Standardbibliothek basieren auf Windows-Synchronisierungsprimitiven und verwenden ConcRT nicht mehr (außer wenn die Zielplattform Windows XP ist). Die in \<mutex> definierten Typen dürfen nicht mit ConcRT-Typen oder Funktionen verwendet werden.

## <a name="syntax"></a>Syntax

```cpp
#include <mutex>
```

## <a name="remarks"></a>Hinweise

> [!NOTE]
> Im Code, der kompiliert wird **"/ CLR"**, dieser Header blockiert.

Die Klassen `mutex` und `recursive_mutex` sind *mutex-Typen*. Ein mutex-Typ verfügt über einen Standardkonstruktor und einen Destruktor, der keine Ausnahmen auslöst. Diese Objekte weisen Methoden auf, die gegenseitigen Ausschluss bereitstellen, wenn mehrere Threads versuchen, das gleiche Objekt zu sperren. Ein mutex-Typ enthält genauer gesagt die `lock`- `try_lock`- und `unlock`-Methoden:

- Die `lock`-Methode blockiert den aufrufenden Thread, bis der Thread in den Besitz von mutex gelangt. Der Rückgabewert wird ignoriert.

- Die `try_lock`-Methode versucht, ohne Blockierung in den Besitz von mutex zu gelangen. Der Rückgabetyp ist in **"bool"** und **"true"** , wenn die Methode den Besitz erlangt, andernfalls **"false"**.

- Die `unlock`-Methode gibt den Besitz von mutex von dem aufrufenden Thread frei.

Sie können mutex-Typen als Typargumente verwenden, um die Vorlagen `lock_guard` und `unique_lock` zu instanziieren. Sie können Objekte dieser Typen als das `Lock`-Argument für die wait-Memberfunktionen in der Vorlage [condition_variable_any](../standard-library/condition-variable-any-class.md) verwenden.

Ein *timed_mutex-Typ* erfüllt die Anforderungen eines mutex-Typs. Darüber hinaus weist er die `try_lock_for` und `try_lock_until` Methoden, die mit einem Argument aufgerufen werden und müssen einen Typ, der konvertiert werden kann, zurückgeben **"bool"**. Ein zeitgesteuerter mutex-Typ kann diese Funktionen mit zusätzlichen Argumenten definieren, vorausgesetzt, dass diese zusätzlichen Argumente über Standardwerte verfügen.

- Die `try_lock_for`-Methode muss mit einem Argument (`Rel_time`) aufgerufen werden können, dessen Typ eine Instanziierung von [chrono::duration](../standard-library/duration-class.md) ist. Die Methode versucht, in den Besitz von mutex zu gelangen, gibt jedoch unabhängig vom Erfolg innerhalb der in `Rel_time` festgelegten Zeit einen Wert zurück. Der zurückgegebene Wert konvertiert in **"true"** , wenn die Methode den Besitz; erhält, andernfalls der Rückgabewert konvertiert in **"false"**.

- Die `try_lock_until`-Methode muss mit einem Argument (`Abs_time`) aufgerufen werden können, dessen Typ eine Instanziierung von [chrono:: time_point](../standard-library/time-point-class.md) ist. Die Methode versucht, in den Besitz von mutex zu gelangen, gibt jedoch unabhängig vom Erfolg nicht später als innerhalb der in `Abs_time` festgelegten Zeit einen Wert zurück. Der zurückgegebene Wert konvertiert in **"true"** , wenn die Methode den Besitz; erhält, andernfalls der Rückgabewert konvertiert in **"false"**.

Ein mutex-Typ wird auch als *sperrbarer Typ* bezeichnet. Wenn er die Memberfunktion `try_lock` nicht bereitstellt, handelt es sich um einen *sperrbaren Basistyp*. Ein timed_mutex-Typ wird auch als *zeitgesteuerter sperrbarer Typ* bezeichnet.

### <a name="classes"></a>Klassen

|Name|Beschreibung|
|----------|-----------------|
|[lock_guard-Klasse](../standard-library/lock-guard-class.md)|Stellt eine Vorlage dar, die zum Erstellen eines Objekts instanziiert werden kann, dessen Destruktor ein `mutex`-Objekt entsperrt.|
|[mutex-Klasse (C++-Standardbibliothek)](../standard-library/mutex-class-stl.md)|Stellt einen mutex-Typ dar. Verwenden Sie Objekte dieses Typs dazu, den gegenseitigen Ausschluss innerhalb eines Programms zu erzwingen.|
|[recursive_mutex-Klasse](../standard-library/recursive-mutex-class.md)|Stellt einen mutex-Typ dar. Das Verhalten von aufrufenden Sperrmethoden für Objekte, die bereits gesperrt sind, ist im Gegensatz zur `mutex`-Klasse klar definiert.|
|[recursive_timed_mutex-Klasse](../standard-library/recursive-timed-mutex-class.md)|Stellt einen zeitgesteuerten mutex-Typ dar. Verwenden Sie Objekte dieses Typs dazu, den gegenseitigen Ausschluss mit zeitbegrenzter Blockierung innerhalb eines Programms zu erzwingen. Im Gegensatz zu Objekten des `timed_mutex`-Typs sind die Auswirkungen von aufrufenden Sperrmethoden für `recursive_timed_mutex`-Objekte klar definiert.|
|[timed_mutex-Klasse](../standard-library/timed-mutex-class.md)|Stellt einen zeitgesteuerten mutex-Typ dar. Verwenden Sie Objekte dieses Typs dazu, den gegenseitigen Ausschluss mit zeitbegrenzter Blockierung innerhalb eines Programms zu erzwingen.|
|[unique_lock-Klasse](../standard-library/unique-lock-class.md)|Stellt eine Vorlage dar, die zum Erstellen von Objekten instanziiert werden kann, die das Sperren und Entsperren von `mutex` verwalten.|

### <a name="functions"></a>Funktionen

|Name|Beschreibung|
|----------|-----------------|
|[call_once](../standard-library/mutex-functions.md#call_once)|Stellt einen Mechanismus zum Aufrufen eines angegebenen aufrufbaren Objekts genau einmal während der Ausführung bereit.|
|[lock](../standard-library/mutex-functions.md#lock)|Versucht, alle Argumente ohne Deadlock zu sperren.|

### <a name="structs"></a>Strukturen

|name|Beschreibung|
|----------|-----------------|
|[adopt_lock_t-Struktur](../standard-library/adopt-lock-t-structure.md)|Stellt einen Typ dar, der zum Definieren eines `adopt_lock`-Elements verwendet wird.|
|[defer_lock_t-Struktur](../standard-library/defer-lock-t-structure.md)|Stellt einen Typ dar, der ein `defer_lock`-Objekt definiert, das zum Auswählen eines überladenen Konstruktors von `unique_lock` verwendet wird.|
|[once_flag-Struktur](../standard-library/once-flag-structure.md)|Stellt eine **Struktur** wird, mit der Vorlagenfunktion `call_once` um sicherzustellen, dass die Initialisierung ist Code auch bei mehreren Ausführungsthreads nur einmal aufgerufen.|
|[try_to_lock_t-Struktur](../standard-library/try-to-lock-t-structure.md)|Stellt eine **Struktur** , definiert ein `try_to_lock` Objekt aus, und dient zum Auswählen eines überladenen Konstruktors von `unique_lock`.|

### <a name="variables"></a>Variablen

|name|Beschreibung|
|----------|-----------------|
|[adopt_lock](../standard-library/mutex-functions.md#adopt_lock)|Stellt ein Objekt dar, das an die Konstruktoren von `lock_guard` und `unique_lock` übergeben werden kann, um anzugeben, dass das auch an den Konstruktor übergebene mutex-Objekt gesperrt ist.|
|[defer_lock](../standard-library/mutex-functions.md#defer_lock)|Stellt ein Objekt dar, das an den Konstruktor für `unique_lock` übergeben werden kann, um anzugeben, dass der Konstruktor das an diesen übergebene mutex-Objekt nicht sperren soll.|
|[try_to_lock](../standard-library/mutex-functions.md#try_to_lock)|Stellt ein Objekt dar, das an den Konstruktor für `unique_lock` übergeben werden kann, um anzugeben, dass der Konstruktor das an diesen übergebene `mutex`-Objekt ohne Blockierung entsperren soll.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
