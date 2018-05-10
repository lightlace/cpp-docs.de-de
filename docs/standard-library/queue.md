---
title: '&lt;queue&gt; | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <queue>
dev_langs:
- C++
helpviewer_keywords:
- queue header
ms.assetid: 24fcf350-eb0e-48cf-9fef-978be1aeda1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ba139e2b50f1dd7c9887701a522a002173c21ee
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="ltqueuegt"></a>&lt;queue&gt;

Definiert die Vorlagenklassen "priority_queue" und "queue" sowie einige unterstützende Vorlagen.

## <a name="syntax"></a>Syntax

```cpp
#include <queue>

```

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator!=](../standard-library/queue-operators.md#op_neq)|Testet, ob das queue-Objekt links vom Operator ungleich dem queue-Objekt rechts vom Operator ist.|
|[operator<](../standard-library/queue-operators.md#op_lt)|Testet, ob das queue-Objekt links vom Operator kleiner ist als das queue-Objekt rechts vom Operator.|
|[operator\<=](../standard-library/queue-operators.md#op_gt_eq)|Testet, ob das queue-Objekt links vom Operator kleiner gleich dem queue-Objekt rechts vom Operator ist.|
|[operator==](../standard-library/queue-operators.md#op_eq_eq)|Testet, ob das queue-Objekt links vom Operator gleich dem queue-Objekt rechts vom Operator ist.|
|[operator>](../standard-library/queue-operators.md#op_gt)|Testet, ob das queue-Objekt links vom Operator größer ist als das queue-Objekt rechts vom Operator.|
|[operator>=](../standard-library/queue-operators.md#op_gt_eq)|Testet, ob das queue-Objekt links vom Operator größer gleich dem queue-Objekt rechts vom Operator ist.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[queue-Klasse](../standard-library/queue-class.md)|Eine Vorlagencontainer-Adapterklasse, die die Funktionalität einschränkt, indem sie den Zugriff auf die vorderen und hinteren Elemente eines zugrunde liegenden Containertyps beschränkt.|
|[priority_queue-Klasse](../standard-library/priority-queue-class.md)|Eine Vorlagencontainer-Adapterklasse, die die Funktionalität einschränkt, indem sie den Zugriff auf das oberste Element eines zugrunde liegenden Containertyps beschränkt, das immer das größte Element ist.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
