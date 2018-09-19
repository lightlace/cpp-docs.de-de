---
title: Auto-Schlüsselwort | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 10952e6360fc8170c59e9a67fe3027622cbea4bc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055525"
---
# <a name="auto-keyword"></a>Auto-Schlüsselwort

Die **automatisch** Schlüsselwort ist ein deklarationsspezifizierer. Der C++-Standard definiert jedoch eine ursprüngliche und eine überarbeitete Bedeutung für dieses Schlüsselwort. Vor Visual C++ 2010 die **automatisch** -Schlüsselwort deklariert eine Variable in der *automatische* Speicherklasse, d. h. eine Variable, die eine lokale Lebensdauer verfügt. Ab Visual C++ 2010 die **automatisch** -Schlüsselwort deklariert eine Variable, deren Typ aus dem Initialisierungsausdruck in der Deklaration abgeleitet wird. Die [/Zc: Auto&#91;-&#93; ](../build/reference/zc-auto-deduce-variable-type.md) -Compileroption steuert die Bedeutung des das **automatisch** Schlüsselwort.

## <a name="syntax"></a>Syntax

```cpp
auto declarator ;
auto declarator initializer;
```

## <a name="remarks"></a>Hinweise

Die Definition der **automatisch** -Schlüsselworts ändert sich in der Programmiersprache C++, aber nicht in der Programmiersprache C.

Die folgenden Themen beschreiben die **automatisch** -Schlüsselwort und die entsprechende Compileroption:

- [automatische](../cpp/auto-cpp.md) wird beschrieben, die neue Definition des der **automatisch** Schlüsselwort.

- [/ Zc: Auto (Variablentyp ableiten)](../build/reference/zc-auto-deduce-variable-type.md) beschreibt die Compileroption, die dem Compiler, welche Definition des mitteilt der **automatisch** Schlüsselwort zu verwenden.

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)