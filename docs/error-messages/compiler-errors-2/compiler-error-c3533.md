---
title: Compilerfehler C3533
ms.date: 11/04/2016
f1_keywords:
- C3533
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
ms.openlocfilehash: 7a567e4396999f98d9e9740db0acf951c443d525
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026304"
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
