---
title: 'Speicherverwaltung: Beispiele für | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], memory allocation
- data structures [MFC]
- arrays [MFC], allocating resources
- objects [MFC], allocating memory
- data structures [MFC], allocating memory
- examples [MFC], memory allocation
- heap allocation [MFC], examples
- memory allocation [MFC], arrays
- MFC, memory management
- struct memory allocation [MFC]
- types [MFC], memory allocation
- memory allocation [MFC], objects
- memory allocation [MFC], examples
- arrays [MFC], memory management
- frame allocation [MFC]
- memory allocation [MFC], data structures
ms.assetid: f10240f8-b698-4c83-9288-97a54318930b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 21efd095a1d8e89c140ef39072a753c300a3043b
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929306"
---
# <a name="memory-management-examples"></a>Speicherverwaltung: Beispiele
In diesem Artikel wird beschrieben, wie MFC für jede der drei typische speicherbelegungen Frame Zuordnungen und Heapzuordnungen ausführt:  
  
-   [Ein Array von bytes](#_core_allocation_of_an_array_of_bytes)  
  
-   [Eine Datenstruktur](#_core_allocation_of_a_data_structure)  
  
-   [Ein Objekt](#_core_allocation_of_an_object)  
  
##  <a name="_core_allocation_of_an_array_of_bytes"></a> Zuordnung eines Arrays von Bytes  
  
#### <a name="to-allocate-an-array-of-bytes-on-the-frame"></a>Ein Array von Bytes auf den Frame zugewiesen werden.  
  
1.  Definieren Sie das Array an, wie im folgenden Code gezeigt. Das Array wird automatisch gelöscht, und der Arbeitsspeicher wieder freigegeben, wenn die Arrayvariable ihren Gültigkeitsbereich verlässt.  
  
     [!code-cpp[NVC_MFC_Utilities#1](../mfc/codesnippet/cpp/memory-management-examples_1.cpp)]  
  
#### <a name="to-allocate-an-array-of-bytes-or-any-primitive-data-type-on-the-heap"></a>Ein Array von Bytes (oder einen beliebigen primitiven Datentyp aufweisen) auf dem Heap zugewiesen werden.  
  
1.  Verwenden der **neue** Operator mit der Arraysyntax, die in diesem Beispiel gezeigt:  
  
     [!code-cpp[NVC_MFC_Utilities#2](../mfc/codesnippet/cpp/memory-management-examples_2.cpp)]  
  
#### <a name="to-deallocate-the-arrays-from-the-heap"></a>Die Arrays aus dem Heap aufgehoben  
  
1.  Verwenden der **löschen** Operator wie folgt:  
  
     [!code-cpp[NVC_MFC_Utilities#3](../mfc/codesnippet/cpp/memory-management-examples_3.cpp)]  
  
##  <a name="_core_allocation_of_a_data_structure"></a> Zuordnung von einer Datenstruktur  
  
#### <a name="to-allocate-a-data-structure-on-the-frame"></a>Eine Datenstruktur auf den Frame zugewiesen werden.  
  
1.  Definieren Sie die Strukturvariable wie folgt:  
  
     [!code-cpp[NVC_MFC_Utilities#4](../mfc/codesnippet/cpp/memory-management-examples_4.cpp)]  
  
     Der von der Struktur belegte Arbeitsspeicher wird freigegeben, wenn sie ihren Gültigkeitsbereich verlässt.  
  
#### <a name="to-allocate-data-structures-on-the-heap"></a>Zuweisen von Datenstrukturen auf dem heap  
  
1.  Verwendung **neue** Datenstrukturen auf dem Heap zugewiesen werden und **löschen** , Zuweisung aufheben können, wie in den folgenden Beispielen gezeigt:  
  
     [!code-cpp[NVC_MFC_Utilities#5](../mfc/codesnippet/cpp/memory-management-examples_5.cpp)]  
  
##  <a name="_core_allocation_of_an_object"></a> Zuweisung eines Objekts  
  
#### <a name="to-allocate-an-object-on-the-frame"></a>Ein Objekt auf den Frame zugewiesen werden.  
  
1.  Deklarieren Sie das Objekt wie folgt:  
  
     [!code-cpp[NVC_MFC_Utilities#6](../mfc/codesnippet/cpp/memory-management-examples_6.cpp)]  
  
     Der Destruktor für das Objekt wird automatisch aufgerufen, wenn das Objekt seinen Gültigkeitsbereich verlässt.  
  
#### <a name="to-allocate-an-object-on-the-heap"></a>Ein Objekt auf dem Heap zugewiesen werden.  
  
1.  Verwenden der **neue** -Operator, der einen Zeiger auf das Objekt zurückgibt, um Objekte auf dem Heap zuzuordnen. Verwenden der **löschen** Operator zu löschen.  
  
     Die folgenden Beispiele für Heap- und davon ausgehen, dass die `CPerson` Konstruktor akzeptiert keine Argumente.  
  
     [!code-cpp[NVC_MFC_Utilities#7](../mfc/codesnippet/cpp/memory-management-examples_7.cpp)]  
  
     Wenn das Argument für die `CPerson` Konstruktor ist ein Zeiger auf **Char**, die Anweisung zum rahmenzuordnung lautet:  
  
     [!code-cpp[NVC_MFC_Utilities#8](../mfc/codesnippet/cpp/memory-management-examples_8.cpp)]  
  
     Die Anweisung für Heapzuordnung ist:  
  
     [!code-cpp[NVC_MFC_Utilities#9](../mfc/codesnippet/cpp/memory-management-examples_9.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherverwaltung: Heapbelegung](../mfc/memory-management-heap-allocation.md)

