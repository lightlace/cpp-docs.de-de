---
title: 'Vorgehensweise: Verbessern der Arbeitsspeicherleistung mithilfe von Alloc und Free'
ms.date: 11/04/2016
helpviewer_keywords:
- Alloc and Free, using [Concurrency Runtime]
- Using Alloc and Free [Concurrency Runtime]
ms.assetid: e1fab9e8-a97d-4104-bead-e95958db79f9
ms.openlocfilehash: 8438e833262d42c6083f48f759501c573a35c772
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142790"
---
# <a name="how-to-use-alloc-and-free-to-improve-memory-performance"></a>Vorgehensweise: Verbessern der Arbeitsspeicherleistung mithilfe von Alloc und Free

In diesem Dokument wird gezeigt, wie die Funktionen "Parallelität [:: Zuweisung](reference/concurrency-namespace-functions.md#alloc) " und "Parallelität [:: Free](reference/concurrency-namespace-functions.md#free) " verwendet werden, um die Speicherleistung zu verbessern In ihm wird die Zeit verglichen, die erforderlich ist, um die Elemente eines Arrays parallel für drei verschiedene Typen umzukehren, für die jeweils die Operatoren `new` und `delete` angegeben sind.

Die Funktionen `Alloc` und `Free` sind besonders dann nützlich, wenn mehrere Threads häufig sowohl `Alloc` als auch `Free` aufrufen. Die Laufzeit besitzt für jeden Thread einen separaten Arbeitsspeichercache. Aus diesem Grund verwaltet die Laufzeit Arbeitsspeicher, ohne dabei Sperren oder Arbeitsspeicherbarrieren zu verwenden.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt drei Typen, die jeweils über die Operatoren `new` und `delete` verfügen. Die `new_delete`-Klasse verwendet die globalen `new` und `delete` Operatoren, die `malloc_free`-Klasse verwendet die C-Lauf Zeitfunktionen [malloc](../../c-runtime-library/reference/malloc.md) und [Free](../../c-runtime-library/reference/free.md) , und die `Alloc_Free`-Klasse verwendet die Concurrency Runtime `Alloc`-und `Free`-Funktionen.

[!code-cpp[concrt-allocators#1](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_1.cpp)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden die Funktionen `swap` und `reverse_array` dargestellt. Die `swap`-Funktion tauscht den Inhalt des Arrays bei den angegebenen Indizes aus. Sie weist Speicher vom Heap für die temporäre Variable zu. Die `reverse_array`-Funktion erstellt ein großes Array und berechnet die Zeit, die erforderlich ist, um dieses Array mehrmals parallel umzukehren.

[!code-cpp[concrt-allocators#2](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_2.cpp)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die `wmain`-Funktion angezeigt, mit der man die Zeit berechnet, die erforderlich ist, damit die `reverse_array`-Funktion auf die Typen `new_delete`, `malloc_free` und `Alloc_Free` reagiert, von denen jeweils ein anderes Speicherbelegungsschema verwendet wird.

[!code-cpp[concrt-allocators#3](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_3.cpp)]

## <a name="example"></a>Beispiel

Im Folgenden finden Sie das vollständige Beispiel.

[!code-cpp[concrt-allocators#4](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_4.cpp)]

In diesem Beispiel wird folgende Beispielausgabe für einen Computer mit vier Prozessoren erzeugt.

```Output
Took 2031 ms with new/delete.
Took 1672 ms with malloc/free.
Took 656 ms with Alloc/Free.
```

In diesem Beispiel stellt der Typ, der die Funktionen `Alloc` und `Free` verwendet, die beste Arbeitsspeicherleistung bereit, da die Funktionen `Alloc` und `Free` zum häufigen Zuordnen und Befreien von Speicherblöcken von mehreren Threads optimiert werden.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `allocators.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio-Eingabe Aufforderungs Fenster aus.

> **cl. exe/EHsc-Zuweisung. cpp**

## <a name="see-also"></a>Weitere Informationen

[Speicherverwaltungsfunktionen](../../parallel/concrt/memory-management-functions.md)<br/>
["Zuweisung"-Funktion](reference/concurrency-namespace-functions.md#alloc)<br/>
[Free-Funktion](reference/concurrency-namespace-functions.md#free)
