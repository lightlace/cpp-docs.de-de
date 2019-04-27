---
title: Auto-Schlüsselwort
ms.date: 11/04/2016
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
ms.openlocfilehash: 3477bd5033fac5b69733db5d6095c1317aac42ee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62284723"
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