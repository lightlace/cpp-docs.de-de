---
title: __unaligned
ms.date: 12/17/2018
f1_keywords:
- __unaligned_cpp
- __unaligned
- _unaligned
helpviewer_keywords:
- __unaligned keyword [C++]
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
ms.openlocfilehash: 8eb1b93aa55601125600b6c69d9bff3d9ca43aa3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62244115"
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

- [Beispiele für die Strukturausrichtung](../build/x64-software-conventions.md#examples-of-structure-alignment)

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)