---
title: vtordisp-Pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.vtordisp
- vtordisp_CPP
helpviewer_keywords:
- pragmas, vtordisp
- vtordisp pragma
ms.assetid: 05b7d73c-43fa-4b62-8c8a-170a9e427391
ms.openlocfilehash: 3c676ab2bfee1b6cf3caff3ab456a4f23f2744c3
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216483"
---
# <a name="vtordisp-pragma"></a>vtordisp-Pragma

**C++Zugeschnitten**

Steuert das Hinzufügen des `vtordisp` ausgeblendeten Erstellungs-/Zerstörungs Verschiebungs Elements.

## <a name="syntax"></a>Syntax

> **#pragma vtordisp (** [ **Push,** ] *n* **)** \
> **#pragma vtordisp (Pop)** \
> **#pragma vtordisp ()** \
> **#pragma vtordisp (** [ **Push,** ] { **on** | **Off** } **)**

### <a name="parameters"></a>Parameter

**Push**\
Überträgt die aktuelle `vtordisp` Einstellung auf den internen compilerstapel und legt die neue `vtordisp` Einstellung auf *n*fest.  Wenn *n* nicht angegeben ist, wird `vtordisp` die aktuelle Einstellung unverändert.

**Chor**\
Entfernt den obersten Datensatz aus dem internen compilerstapel und stellt die `vtordisp` Einstellung auf dem entfernten Wert wieder her.

*n*\
Gibt den neuen Wert für die `vtordisp` Einstellung an. Mögliche Werte sind 0, 1 oder 2, was den `/vd0`Compileroptionen, `/vd2` `/vd1`und entspricht. Weitere Informationen finden Sie unter [/VD (Konstruktions Verschiebungen deaktivieren)](../build/reference/vd-disable-construction-displacements.md).

**auf**\
Entspricht `#pragma vtordisp(1)`.

**abgeschrieben**\
Entspricht `#pragma vtordisp(0)`.

## <a name="remarks"></a>Hinweise

Das **vtordisp** -Pragma gilt nur für Code, der virtuelle Basen verwendet. Wenn eine abgeleitete Klasse eine virtuelle Funktion überschreibt, die sie von einer virtuellen Basisklasse erbt, und wenn ein Konstruktor oder Destruktor der abgeleiteten Klasse die Funktion mithilfe eines Zeigers auf die virtuelle Basisklasse aufruft, kann der Compiler zusätzliche ausgeblendete `vtordisp`-Felder in die Klassen mit virtuellen Basen einführen.

Das **vtordisp** -Pragma wirkt sich auf das Layout der Klassen aus, die ihm folgen. Die `/vd0`Optionen `/vd1`, und`/vd2` geben das gleiche Verhalten für die gesamten Module an. Durch Angeben von 0 oder **Off** werden die `vtordisp` ausgeblendeten Elemente unterdrückt Deaktivieren Sie **vtordisp** nur dann, wenn es keine Möglichkeit gibt, dass die Konstruktoren und debugtoren der Klasse virtuelle Funktionen für das Objekt, `this` auf das der Zeiger verweist, aufruft.

Bei Angabe von 1 oder **on**(Standardeinstellung) werden `vtordisp` die ausgeblendeten Member aktiviert, wo Sie erforderlich sind.

Durch Angeben von 2 werden `vtordisp` die ausgeblendeten Elemente für alle virtuellen Basen mit virtuellen Funktionen aktiviert.  `#pragma vtordisp(2)`Möglicherweise ist erforderlich, um die korrekte Leistung von **dynamic_cast** auf einem teilweise konstruierten Objekt sicherzustellen. Weitere Informationen finden Sie unter [Compilerwarnung (Stufe 1) C4436](../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md).

`#pragma vtordisp()`, ohne Argumente, stellt die Einstellung `vtordisp` für die ursprüngliche Einstellung wieder her.

```cpp
#pragma vtordisp(push, 2)
class GetReal : virtual public VBase { ... };
#pragma vtordisp(pop)
```

**End C++ -Specific**

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
