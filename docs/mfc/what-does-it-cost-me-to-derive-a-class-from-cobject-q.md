---
title: Welcher Overhead entsteht beim Ableiten einer Klasse von CObject? | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- CObject class [MFC], overhead of derived classes [MFC]
ms.assetid: 9b92c98b-b3dd-48a7-9d24-c3b8554edf90
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3ffff35cdef6cf2f730687334bbb56bc078371a7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="what-does-it-cost-me-to-derive-a-class-from-cobject"></a>Welcher Overhead entsteht beim Ableiten einer Klasse von CObject?
Der Aufwand beim Ableiten einer Klasse [CObject](../mfc/reference/cobject-class.md) ist minimal. Die abgeleitete Klasse erbt nur vier virtuelle Funktionen und eine einzelne [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse: Häufig gestellte Fragen](../mfc/cobject-class-frequently-asked-questions.md)
