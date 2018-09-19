---
title: __unaligned | Microsoft-Dokumentation
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
ms.openlocfilehash: 9593a0b3c6e6980f5be2ce9dcf13e505e94dcace
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040195"
---
# <a name="unaligned"></a>__unaligned

**Microsoft-spezifisch**. Wenn Sie einen Zeiger mit deklarieren die **__unaligned** Modifizierer, nimmt der Compiler an, dass der Zeiger auf Daten verweist, die nicht ausgerichtet ist. Daher wird für die Plattform angemessene Code wird generiert, um die Behandlung von nicht ausgerichteten Lesevorgänge und schreibt über den Zeiger.

## <a name="remarks"></a>Hinweise

Dieser Modifizierer beschreibt die Ausrichtung der Daten vom Zeiger adressiert wird. der Zeiger selbst wird angenommen, dass ausgerichtet werden.

Die Notwendigkeit der **__unaligned** Schlüsselwort unterscheidet sich von Plattform und Umgebung. Daten entsprechend kennzeichnen kann zu Problemen, die von Leistungseinbußen zur Folge haben bis hin zu Hardware-Fehlern führen. Die **__unaligned** Modifizierer ist nicht gültig für die X86 Plattform.

Weitere Informationen zur Ausrichtung finden Sie unter:

- [align](../cpp/align-cpp.md)

- [__alignof-Operator](../cpp/alignof-operator.md)

- [pack](../preprocessor/pack.md)

- [/Zp (Strukturmemberausrichtung)](../build/reference/zp-struct-member-alignment.md)

- [Beispiele für die Strukturausrichtung](../build/examples-of-structure-alignment.md)

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)