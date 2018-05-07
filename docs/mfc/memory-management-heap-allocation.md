---
title: 'Speicherverwaltung: Heap Zuordnung | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory [MFC], detecting leaks
- delete operator [MFC], using with debug MFC
- heap allocation [MFC], described
- memory allocation [MFC], heap memory
- memory leaks [MFC], detecting
- new operator [MFC], using with debug MFC
- heap allocation [MFC]
- detecting memory leaks [MFC]
ms.assetid: a5d949c6-1b79-476e-9c66-513a558203d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 99df4a50f021e0981354a5d316606729bb824d94
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="memory-management-heap-allocation"></a>Speicherverwaltung: Heapbelegung
Für die Zuordnung arbeitsspeicheranforderungen des Programms wird im Heap reserviert. Es ist ein Bereich, abgesehen von den Programmcode und den Stapel. Standard-C-Programmen verwenden Sie die Funktionen `malloc` und **freien** zu reservieren und Freigeben von Speicher für den Heap. Die Debugversion von MFC bietet geänderte Versionen von den integrierten C++-Operatoren **neue** und **löschen** reservieren und Freigeben von Objekten im Heap Arbeitsspeicher.  
  
 Bei Verwendung von **neue** und **löschen** anstelle von `malloc` und **freien**, können Sie die Klassenbibliothek Speicher-Management-debugverbesserungen nutzen , die hilfreich beim Erkennen von Speicherverlusten sein können. Beim Erstellen des Programms mit der endgültigen Produktversion von den Standardversionen von MFC die **neue** und **löschen** Operatoren bieten eine effiziente Methode zum Belegen und Freigeben von Arbeitsspeicher (der endgültigen Produktversion von MFC stellt keine geänderte Versionen dieser Operatoren bereit).  
  
 Beachten Sie, dass die Gesamtgröße der Objekte, die auf dem Heap reserviert nur von Ihrem System verfügbaren virtuellen Speicher beschränkt ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherverwaltung](../mfc/memory-management.md)

