---
title: Vermeiden von Heapkonflikten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- heap contention
ms.assetid: 797129d7-5f8c-4b0e-8974-bb93217e9ab5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a4f01bdbbc14e09fe8f9823eed738556ee876376
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762250"
---
# <a name="avoidance-of-heap-contention"></a>Vermeiden von Heapkonflikten

Der Standardzeichenfolgen-Manager von MFC und ATL sind einfache Wrapper für einen globalen Heap. Dieser globale Heap ist vollständig threadsicher, dies bedeutet, dass mehrere Threads zuweisen und freier Arbeitsspeicher daraus gleichzeitig, ohne den Heap beschädigen können. Um Threadsicherheit zu bieten, muss der Heap Serialisierung des Zugriffs auf sich selbst. Dies erfolgt in der Regel mit einem kritischen Abschnitt oder einer ähnlichen Mechanismus zum Sperren. Wenn zwei Threads gleichzeitig auf dem Heap versuchen, wird ein Thread blockiert, bis der andere Thread-Anforderung abgeschlossen ist. Bei vielen Anwendungen diese Situation tritt selten auf, und die Auswirkungen auf die Leistung der Mechanismus zum Sperren des Heaps sind zu vernachlässigen. Allerdings für Anwendungen, die den Heap häufig aus mehreren Threads zugreifen Konflikte bezüglich des Heaps Sperre der Anwendung verursachen kann langsamer, als wenn es Singlethread-(gilt auch für Computer mit mehreren CPUs) ausgeführt werden.

Anwendungen, die [CStringT](../atl-mfc-shared/reference/cstringt-class.md) sind besonders anfällig, Heapkonflikten da Vorgänge auf `CStringT` Objekte erfordern häufig neuzuordnung des Zeichenfolgenpuffers.

Eine Möglichkeit zur Eindämmung der Heapkonflikte zwischen den Threads ist jeder Thread, der Zeichenfolgen aus einem privaten, lokalen Thread-Heap zugeordnet haben. So lange Zeichenfolgen zugeordnet werden Zuweisung für einen bestimmten Thread nur in diesem Thread, die Zuweisung muss nicht threadsicher sein.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht eine Threadprozedur, die für Zeichenfolgen, die auf diesem Thread verwendet einen eigenen privaten nicht threadsichere-Heap reserviert:

[!code-cpp[NVC_ATLMFC_Utilities#182](../atl-mfc-shared/codesnippet/cpp/avoidance-of-heap-contention_1.cpp)]

## <a name="comments"></a>Kommentare

Mehrere Threads können mit diesem Verfahren der gleichen Thread ausgeführt werden, da jeder Thread über einen eigenen Heap hat es gibt jedoch keine Konflikte zwischen Threads. Darüber hinaus bietet die Tatsache, dass jeder Heap nicht threadsicher ist deutlich die Leistung aus, selbst wenn nur eine Kopie der Thread ausgeführt wird. Dies ist das Ergebnis des Heaps nicht teuer interlocked-Vorgänge zum Schutz vor gleichzeitigen Zugriff verwenden.

Für eine kompliziertere Threadprozedur kann es praktisch sein, einen Zeiger auf die Threadverwaltung Zeichenfolge in einem Slot der Thread-Speicher (TLS) gespeichert sein. Dadurch können andere Funktionen, die durch die Threadprozedur zeichenfolgenmanagers des Threads den Zugriff auf aufgerufen.

## <a name="see-also"></a>Siehe auch

[Speicherverwaltung mit CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)

