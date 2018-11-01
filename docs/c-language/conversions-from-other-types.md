---
title: Konvertierungen von anderen Typen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- values, converting
- type casts, conversion
ms.assetid: 30fbd974-8f5a-4b70-ac44-d3937b96b702
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b443526248eb09accce8b35133235c71c06c2627
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094584"
---
# <a name="conversions-from-other-types"></a>Konvertierungen von anderen Typen

Da ein **enum**-Wert definitionsgemäß ein **int**-Wert ist, sind Konvertierungen aus und in einen **enum**-Wert identisch mit denen für den Typ **int**. Für den Microsoft C-Compiler entspricht eine Ganzzahl **long**.

**Microsoft-spezifisch**

Es sind keine Konvertierungen zwischen Struktur- oder Union-Typen zulässig.

Jeder Wert kann in den Typ **void** konvertiert werden, aber das Ergebnis einer solchen Konvertierung kann nur in einem Kontext verwendet werden, in dem ein Ausdruckswert verworfen wird, z.B. in einer Ausdrucksanweisung.

Der **void**-Typ hat definitionsgemäß keinen Wert. Daher kann er nicht in einen anderen Typ konvertiert werden, und andere Typen können nicht durch Zuweisung in **void** konvertiert werden. Sie können jedoch explizit einen Wert in den Typ **void** umwandeln, wie in [Typumwandlungskonvertierungen](../c-language/type-cast-conversions.md) erläutert.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Zuweisungskonvertierungen](../c-language/assignment-conversions.md)
