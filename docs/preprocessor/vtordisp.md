---
title: vtordisp
ms.date: 10/18/2018
f1_keywords:
- vc-pragma.vtordisp
- vtordisp_CPP
helpviewer_keywords:
- pragmas, vtordisp
- vtordisp pragma
ms.assetid: 05b7d73c-43fa-4b62-8c8a-170a9e427391
ms.openlocfilehash: 67c6c329bcee75012f6075334760925eca945501
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59034377"
---
# <a name="vtordisp"></a>vtordisp

**C++-spezifisch**

Steuert das Hinzufügen ausgeblendeter vtordisp-Member zur Konstruktor-/Destruktorverschiebung.

## <a name="syntax"></a>Syntax

```cpp
#pragma vtordisp([push,] n)
#pragma vtordisp(pop)
#pragma vtordisp()
#pragma vtordisp([push,] {on | off})
```

### <a name="parameters"></a>Parameter

*push*<br/>
Legt die aktuelle Vtordisp-Einstellung auf dem internen compilerstapel ab und legt die neue Vtordisp-Einstellung auf *n*.  Wenn *n* nicht angegeben ist, wird die aktuelle Vtordisp-Einstellung wird nicht geändert.

*pop*<br/>
Entfernt den obersten Datensatz aus dem internen Compilerstapel und setzt die vtordisp-Einstellung auf den entfernten Wert zurück.

*n*<br/>
Gibt den neuen Wert für die vtordisp-Einstellung an. Mögliche Werte sind 0, 1 oder 2, entsprechend der `/vd0`, `/vd1`, und `/vd2` Compileroptionen. Weitere Informationen finden Sie unter [/VD (Konstruktionsverschiebungen deaktivieren)](../build/reference/vd-disable-construction-displacements.md).

*on*<br/>
Entspricht `#pragma vtordisp(1)`.

*off*<br/>
Entspricht `#pragma vtordisp(0)`.

## <a name="remarks"></a>Hinweise

Die **Vtordisp** Pragma gilt nur für Code, der virtuelle Basen verwendet. Wenn eine abgeleitete Klasse überschreibt eine virtuelle Funktion, die sie von einer virtuellen Basisklasse erbt, und wenn ein Konstruktor oder Destruktor für die abgeleitete Klasse diese Funktion mithilfe eines Zeigers auf die virtuelle Basisklasse aufruft, kann der Compiler zusätzliche ausgeblendete einführen**Vtordisp** Felder in Klassen mit virtuellen Basen.

Die **Vtordisp** Pragma wirkt sich auf das Layout der Klassen, die folgen. Die `/vd0`, `/vd1`, und `/vd2` Optionen geben dasselbe Verhalten für vollständige Module. Durch den Wert 0 oder *aus* unterdrückt die ausgeblendeten **Vtordisp** Member. Deaktivieren Sie **Vtordisp** nur gibt es keine Möglichkeit, die Konstruktoren und Destruktoren der Klasse virtuelle Aufrufen für das Objekt verweist Funktionen der **dies** Zeiger.

Angeben von 1 oder *auf*, Standard, ermöglicht die ausgeblendeten **Vtordisp** Mitglieder, wo sie erforderlich sind.

Angeben von 2 ermöglicht die ausgeblendeten **Vtordisp** Elemente für alle virtuellen Basen mit virtuellen Funktionen.  `vtordisp(2)` Möglicherweise müssen Sie die richtige Leistung sicherzustellen **Dynamic_cast** auf einem teilweise konstruierten Objekt. Weitere Informationen finden Sie unter [Compilerwarnung (Stufe 1) C4436](../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md).

`#pragma vtordisp()`, ohne Argumente, setzt die vtordisp-Einstellung auf die ursprüngliche Einstellung zurück.

```cpp
#pragma vtordisp(push, 2)
class GetReal : virtual public VBase { ... };
#pragma vtordisp(pop)
```

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)