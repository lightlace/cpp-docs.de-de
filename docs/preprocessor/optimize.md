---
title: optimize
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.optimize
- optimize_CPP
helpviewer_keywords:
- pragmas, optimize
- optimize pragma
ms.assetid: cb13c1cc-186a-45bc-bee7-95a8de7381cc
ms.openlocfilehash: 65948f2b466bdd40bd753dbba99e2e235c57b0f6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615864"
---
# <a name="optimize"></a>optimize

Gibt die Optimierungen an, die für jede einzelne Funktion durchgeführt werden sollen.

## <a name="syntax"></a>Syntax

```
#pragma optimize( "[optimization-list]", {on | off} )
```

## <a name="remarks"></a>Hinweise

Die **optimieren** -Pragma muss außerhalb der Funktion angezeigt werden und wird wirksam, die erste Funktion definiert, nachdem das Pragma angezeigt wird. Die *auf* und *aus* -Argumenten werden Optionen, die im angegebenen aktiviert die *Optimierungsliste* ein- oder ausschalten.

Die *Optimierungsliste* 0 (null) oder mehrere Parameter in der folgenden Tabelle aus.

### <a name="parameters-of-the-optimize-pragma"></a>Parameter des optimize-Pragmas

|Parameter|Typ der Optimierung|
|--------------------|--------------------------|
|*g*|Aktivieren globale Optimierungen.|
|*s* oder *t*|Geben kurze oder schnelle Sequenzen von Computercode an.|
|*y*|Generieren Framezeiger im Programmstapel.|

Hierbei handelt es sich um dieselben Buchstaben verwendet werden, mit der [/o](../build/reference/o-options-optimize-code.md) Compileroptionen. Beispielsweise ist folgendes Pragma mit der `/Os`-Compileroption identisch:

```
#pragma optimize( "ts", on )
```

Mithilfe der **optimieren** Pragma mit einer leeren Zeichenfolge (**""**) ist eine besondere Form der Anweisung:

Bei Verwendung der *aus* Parameter alle Optimierungen, *g*, *s*, *t*, und *y*, deaktiviert.

Bei Verwendung der *auf* Parameter, die Optimierungen auf die zurückgesetzt, die Sie angegeben haben, mit der [/o](../build/reference/o-options-optimize-code.md) -Compileroption.

```
#pragma optimize( "", off )
.
.
.
#pragma optimize( "", on )
```

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)