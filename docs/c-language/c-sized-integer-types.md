---
title: Angepasste C-Ganzzahltypen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- sized integer types
ms.assetid: 0d6199b4-d0ab-4e8c-a769-785f5afb92eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 037ff61dbe1d1d42d8b0c751fcdc83f01a8dd112
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101418"
---
# <a name="c-sized-integer-types"></a>C-Ganzzahltypen (angepasst)

**Microsoft-spezifisch**

Microsoft C bietet Unterstützung für ganzzahlige Typen mit angegebener Größe. Sie können 8-, 16-, 32- oder 64-Bit-Integer-Variablen deklarieren, indem Sie den __int*n*-Typbezeichner verwenden, wobei *n* die Größe der ganzzahligen Variable (in Bit) ist. Der Wert von *n* kann 8, 16, 32 oder 64 sein. Im folgenden Beispiel wird eine Variable für jeden der vier Typen der nach Größe angepassten Ganzzahlen deklariert:

```
__int8 nSmall;      // Declares 8-bit integer
__int16 nMedium;    // Declares 16-bit integer
__int32 nLarge;     // Declares 32-bit integer
__int64 nHuge;      // Declares 64-bit integer
```

Die ersten drei Typen der nach Größe angepassten Ganzzahlen sind Synonyme für die ANSI-Typen, die die gleichen Größe haben und nützlich für das Schreiben von übertragbarem Code sind, der sich auf vielen verschiedenen Plattformen genau gleich verhält. Beachten Sie, dass der __int8-Datentyp mit dem Typ „char“ synonym ist, \___int16 mit dem Typ „short“ synonym ist und \___int32 mit dem Typ „int“ synonym ist. Der \___int64-Typ verfügt über keine äquivalente ANSI-Entsprechung.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md)