---
title: Compilerfehler C3533
ms.date: 11/04/2016
f1_keywords:
- C3533
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
ms.openlocfilehash: 59ceea942d9165f6f7c6161032e96404bc0dcba7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547250"
---
# <a name="compiler-error-c3533"></a>Compilerfehler C3533

'Typ': ein Parameter keinen Typ, der "auto" enthält

Parameter-Methode oder die Vorlage kann nicht deklariert werden, mit der `auto` Schlüsselwort Wenn standardmäßig [/Zc: Auto](../../build/reference/zc-auto-deduce-variable-type.md) Compileroption aktiviert ist.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Entfernen Sie die `auto` -Schlüsselwort aus der Parameterdeklaration.

## <a name="example"></a>Beispiel

Im folgende Beispiel ergibt C3533, da es sich um einen Funktionsparameter mit deklariert die `auto` -Schlüsselwort, und es wird mit kompiliert **/Zc: Auto**.

```
// C3533a.cpp
// Compile with /Zc:auto
void f(auto j) {} // C3533
```

## <a name="example"></a>Beispiel

Im folgende Beispiel ergibt C3533 in C ++ 14-Modus, da er deklariert, dass einen Vorlagenparameter, mit der `auto` -Schlüsselwort, und es wird mit kompiliert **/Zc: Auto**. (In C ++ 17 ist dies eine gültige Definition einer Klassenvorlage mit einem einzelvorlage Nichttyp-Parameter, dessen Typ abgeleitet wird.)

```
// C3533b.cpp
// Compile with /Zc:auto
template<auto T> class C {}; // C3533
```

## <a name="see-also"></a>Siehe auch

[Auto-Schlüsselwort](../../cpp/auto-keyword.md)<br/>
[/Zc:auto (Variablentyp ableiten)](../../build/reference/zc-auto-deduce-variable-type.md)
