---
title: Compilerfehler C3533 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3533
dev_langs:
- C++
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6201f59e3ccefaa920f79f9b9889bd187fb2e0b0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042558"
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
