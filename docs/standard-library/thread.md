---
title: '&lt;Thread&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- <thread>
dev_langs:
- C++
ms.assetid: 0c858405-4efb-449d-bf76-70d3693c9234
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b5fcf5f9115e87a7608455c78b3bef4ec6895221
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="ltthreadgt"></a>&lt;thread&gt;

Schließen Sie den Standardheader \<Thread > zum Definieren der Klasse `thread` und verschiedene unterstützende Funktionen.

## <a name="syntax"></a>Syntax

```cpp
#include <thread>
```

## <a name="remarks"></a>Hinweise

> [!NOTE]
> In Code, der kompiliert wurde **"/ CLR"**, dieser Header blockiert.

Die `__STDCPP_THREADS__` -Makro wird definiert als einen Wert ungleich NULL, um anzugeben, dass Threads von dieser Header unterstützt werden.

## <a name="members"></a>Member

### <a name="public-classes"></a>Öffentliche Klassen

|Name|Beschreibung|
|----------|-----------------|
|[thread-Klasse](../standard-library/thread-class.md)|Definiert ein Objekt, das zum Überwachen und Verwalten eines Ausführungsthreads in einer Anwendung verwendet wird.|

### <a name="public-structures"></a>Öffentliche Strukturen

|name|Beschreibung|
|----------|-----------------|
|[Hash-Struktur (C++-Standardbibliothek)](../standard-library/hash-structure-stl.md)|Definiert eine Memberfunktion, die einen Wert zurückgibt, die durch nicht eindeutig bestimmt ist eine `thread::id`. Die Member-Funktion definiert einen [Hash](../standard-library/hash-class.md) Funktion für die Zuordnung von Werten des Typs `thread::id` auf eine Verteilung von Indexwerten.|

### <a name="public-functions"></a>Öffentliche Funktionen

|name|Beschreibung|
|----------|-----------------|
|[get_id](../standard-library/thread-functions.md#get_id)|Weist den aktuellen Ausführungsthread eindeutig aus.|
|[sleep_for](../standard-library/thread-functions.md#sleep_for)|Blockiert den aufrufenden Thread.|
|[sleep_until](../standard-library/thread-functions.md#sleep_until)|Blockiert den aufrufenden Thread mindestens bis zum angegebenen Zeitpunkt.|
|[swap](../standard-library/thread-functions.md#swap)|Tauscht die Zustände von zwei `thread` Objekte.|
|[yield](../standard-library/thread-functions.md#yield)|Signalisiert dem Betriebssystem, andere Threads auszuführen, auch wenn der aktuelle Thread normalerweise weiterhin ausgeführt werden würde.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[Operator > =-Operator](../standard-library/thread-operators.md#op_gt_eq)|Bestimmt, ob ein `thread::id`-Objekt größer als oder gleich einem anderen Objekt ist.|
|[Operator >-Operator](../standard-library/thread-operators.md#op_gt)|Bestimmt, ob ein `thread::id`-Objekt größer als ein anderes Objekt ist.|
|[Operator < =-Operator](../standard-library/thread-operators.md#op_lt_eq)|Bestimmt, ob ein `thread::id`-Objekt kleiner als oder gleich einem anderen Objekt ist.|
|[Operator <-Operator](../standard-library/thread-operators.md#op_lt)|Bestimmt, ob ein `thread::id`-Objekt kleiner als ein anderes Objekt ist.|
|[Operator! =-Operator](../standard-library/thread-operators.md#op_neq)|Überprüft zwei `thread::id`-Objekte auf Ungleichheit.|
|[Operator ==-Operator](../standard-library/thread-operators.md#op_eq_eq)|Überprüft zwei `thread::id`-Objekte auf Gleichheit.|
|[Operator << Operator](../standard-library/thread-operators.md#op_lt_lt)|Fügt eine Textdarstellung eines `thread::id`-Objekts in einen Stream ein.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
