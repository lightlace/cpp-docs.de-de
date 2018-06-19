---
title: __unaligned | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __unaligned_cpp
dev_langs:
- C++
helpviewer_keywords:
- __unaligned keyword [C++]
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d73b082b9f41d03eb0b1a8c9fe772351ff4da91f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32420908"
---
# <a name="unaligned"></a>__unaligned

**Microsoft-spezifisch**. Wenn Sie einen Zeiger mit dem `__unaligned`-Modifizierer deklarieren, geht der Compiler davon aus, dass der Zeiger auf Daten verweist, die nicht ausgerichtet sind. Folglich Plattform entsprechende Code wird generiert, um das Behandeln von nicht ausgerichteten Lesevorgänge und Schreibvorgänge, die aufgrund der Zeiger.

## <a name="remarks"></a>Hinweise

Dieser Modifizierer beschreibt die Ausrichtung der Daten vom Zeiger adressiert wird. wird davon ausgegangen, dass der Zeiger selbst ausgerichtet werden.

Die Notwendigkeit der `__unaligned` Schlüsselwort variiert je nach Plattform und Umgebung. Daten entsprechend kennzeichnen, können Probleme, die im Bereich von Leistungseinbußen bis festgestellte Hardwarefehler kommen. Die `__unaligned` Modifizierer ist nicht gültig für die X86 Plattform.

Weitere Informationen zur Ausrichtung finden Sie unter:

- [align](../cpp/align-cpp.md)

- [__alignof-Operator](../cpp/alignof-operator.md)

- [pack](../preprocessor/pack.md)

- [/Zp (Strukturmemberausrichtung)](../build/reference/zp-struct-member-alignment.md)

- [Beispiele für die Strukturausrichtung](../build/examples-of-structure-alignment.md)

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)
