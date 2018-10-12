---
title: __unaligned | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/10/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __unaligned_cpp
- __unaligned
- _unaligned
dev_langs:
- C++
helpviewer_keywords:
- __unaligned keyword [C++]
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 444bc3372b22676cacb3ee89b9c0ad92000cedcc
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161215"
---
# <a name="unaligned"></a>__unaligned

**Microsoft-spezifisch**. Wenn Sie einen Zeiger mit deklarieren die **__unaligned** Modifizierer, nimmt der Compiler an, dass der Zeiger auf Daten verweist, die nicht ausgerichtet ist. Daher wird für die Plattform angemessene Code wird generiert, um die Behandlung von nicht ausgerichteten Lesevorgänge und schreibt über den Zeiger.

## <a name="remarks"></a>Hinweise

Dieser Modifizierer beschreibt die Ausrichtung der Daten vom Zeiger adressiert wird. der Zeiger selbst wird angenommen, dass ausgerichtet werden.

Die Notwendigkeit der **__unaligned** Schlüsselwort unterscheidet sich von Plattform und Umgebung. Daten entsprechend kennzeichnen kann zu Problemen, die von Leistungseinbußen zur Folge haben bis hin zu Hardware-Fehlern führen. Die **__unaligned** Modifizierer ist nicht gültig für die X86 Plattform.

Für die Kompatibilität mit früheren Versionen **_unaligned** ist ein Synonym für **__unaligned** , wenn Compileroption [/Za \(spracherweiterungen deaktivieren)](../build/reference/za-ze-disable-language-extensions.md) angegeben wird.

Weitere Informationen zur Ausrichtung finden Sie unter:

- [align](../cpp/align-cpp.md)

- [__alignof-Operator](../cpp/alignof-operator.md)

- [pack](../preprocessor/pack.md)

- [/Zp (Strukturmemberausrichtung)](../build/reference/zp-struct-member-alignment.md)

- [Beispiele für die Strukturausrichtung](../build/examples-of-structure-alignment.md)

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)