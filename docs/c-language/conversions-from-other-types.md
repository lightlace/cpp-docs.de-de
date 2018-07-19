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
ms.openlocfilehash: e919782022ee64f657611a14d6eae6173a67b8c0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32382678"
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
