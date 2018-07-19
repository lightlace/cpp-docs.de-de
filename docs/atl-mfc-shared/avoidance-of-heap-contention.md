---
title: Vermeidung von Heapkonflikten | Microsoft Docs
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
ms.openlocfilehash: 731fcb2328f789e5c487dc56510bbd6f7ec049ea
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358084"
---
# <a name="avoidance-of-heap-contention"></a>Vermeidung von Heapkonflikten
Die Standardzeichenfolgen-Manager von MFC und ATL sind einfache Wrapper auf einem globalen Heap. Dieser globale Heap ist vollständig threadsicher, was bedeutet, dass mehrere Threads können reservieren und Freigeben von Arbeitsspeicher daraus gleichzeitig ohne Beschädigung im Heap an. Um Threadsicherheit zu gewährleisten, muss der Heap die Serialisierung des Zugriffs auf sich selbst. Dies wird normalerweise mit einem kritischen Abschnitt oder einer ähnlichen Sperrmechanismus erreicht. Wenn zwei Threads gleichzeitig versuchen, gleichzeitig auf den Heap zugreifen, wird ein Thread blockiert, bis der andere Thread-Anforderung abgeschlossen ist. Für viele Anwendungen diese Situation tritt selten auf und die Beeinträchtigung der Leistung des Heaps Sperrmechanismus sind zu vernachlässigen. Allerdings kann für Anwendungen, die den Heap aus mehreren Threads häufig zugreifen Konflikte auf dem Heap Sperre der Anwendung verursachen langsamer, als wenn es Singlethread (gilt auch für Computer mit mehreren CPUs) ausgeführt.  
  
 Anwendungen, die [CStringT](../atl-mfc-shared/reference/cstringt-class.md) sind besonders anfällig für Heapkonflikte da Vorgänge für `CStringT` Objekte erfordern häufig neuzuordnung des Zeichenfolgenpuffers.  
  
 Eine Möglichkeit zur Eindämmung der Heapkonflikte zwischen Threads ist jeder Thread Zeichenfolgen aus einem privaten, lokalen Thread-Heap zuweisen. Solange die Zeichenfolgen mit zugeordnet Zuweisung für einen bestimmten Thread verwendet werden nur in diesem Thread, der Zuweisung muss nicht threadsicher.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht eine Threadprozedur, die weist einen eigenen privaten Heap mit Thread-sichere für Zeichenfolgen in diesem Thread verwenden:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#182](../atl-mfc-shared/codesnippet/cpp/avoidance-of-heap-contention_1.cpp)]  
  
## <a name="comments"></a>Kommentare  
 Mehrere Threads können über diesen Thread Verfahren ausgeführt werden, da jeder Thread über einen eigenen Heap hat es gibt jedoch kein Konflikt zwischen Threads. Darüber hinaus bietet die Tatsache, dass jeder Heap nicht threadsicher ist deutlich die Leistung aus, auch wenn nur eine Kopie der Thread ausgeführt wird. Dies ist das Ergebnis des Heaps nicht aufwendig interlocked-Vorgänge verwenden, um den gleichzeitigen Zugriff zu schützen.  
  
 Für eine komplexere Threadprozedur kann es praktisch sein, einen Zeiger auf die Threadverwaltung Zeichenfolge in einen Slot des threadlokalen Speichers (TLS) gespeichert sein. Dadurch können andere von Zeichenfolgen-Manager für den Thread den Zugriff auf die Threadprozedur aufgerufenen Funktionen.  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherverwaltung mit CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)

