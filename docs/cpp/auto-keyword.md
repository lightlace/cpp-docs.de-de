---
title: Auto-Schlüsselwort
ms.date: 05/07/2019
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
ms.openlocfilehash: a695c33ab55601bb8d81b00f963646f6a48f09d5
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222248"
---
# <a name="auto-keyword"></a>Auto-Schlüsselwort

Die **automatisch** Schlüsselwort ist ein deklarationsspezifizierer. Der C++-Standard definiert jedoch eine ursprüngliche und eine überarbeitete Bedeutung für dieses Schlüsselwort. Bevor Sie Visual Studio 2010 die **automatisch** -Schlüsselwort deklariert eine Variable in der *automatische* Speicherklasse, d. h. eine Variable, die eine lokale Lebensdauer verfügt. Beginnend mit Visual Studio 2010 die **automatisch** -Schlüsselwort deklariert eine Variable, deren Typ aus dem Initialisierungsausdruck in der Deklaration abgeleitet wird. Die [/Zc: Auto&#91;-&#93; ](../build/reference/zc-auto-deduce-variable-type.md) -Compileroption steuert die Bedeutung des das **automatisch** Schlüsselwort.

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