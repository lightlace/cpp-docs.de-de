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
ms.openlocfilehash: 9f5240fc59f59a71ddb3d18b67fadf3463a0d1ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328171"
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