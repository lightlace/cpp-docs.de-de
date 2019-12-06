---
title: C-Funktionsdefinitionen
ms.date: 11/04/2016
helpviewer_keywords:
- function declarators
- function definitions
- declaring functions, about function declarations
- declaring functions, declarators
- functions [C], parameters
- declarators, functions
- function parameters, function definitions
- function body
- declaring functions, variables
ms.assetid: ebab23c8-6eb8-46f3-b21d-570cd8457a80
ms.openlocfilehash: 5cf56375df417ac68b3e03d00f2bd7770ee571e8
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857137"
---
# <a name="c-function-definitions"></a>C-Funktionsdefinitionen

Eine Funktionsdefinition gibt den Namen der Funktion, die Typen und die Zahl der Parameter, die sie erwartungsgemäß empfangen wird, und ihren Rückgabetyp an. Eine Funktionsdefinition enthält auch einen Funktionsrumpf mit den Deklarationen ihrer lokalen Variablen und die Anweisungen, die bestimmen, was die Funktion durchführt.

## <a name="syntax"></a>Syntax

*translation-unit*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*external-declaration* <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*translation-unit* *external-declaration*

*external-declaration*: /\* Nur für externen (Datei-) Bereich zulässig \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*function-definition*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration*

*function-definition*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers*<sub>opt</sub> *attribute-seq*<sub>opt</sub> *declarator* *declaration-list*<sub>opt</sub> *compound-statement*

/\* *Attribute-"-* " ist eine Microsoft-spezifische \*/

Prototypparameter sind:

*declaration-specifiers*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*storage-class-specifier* *declaration-specifiers*<sub>opt</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*type-specifier* *declaration-specifiers*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*type-qualifier* *declaration-specifiers*<sub>opt</sub>

*declaration-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-list* *declaration*

*declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*pointer*<sub>opt</sub> *direct-declarator*

*direct-declarator*:/\* Ein Funktionsdeklarator \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*direct-declarator*  **(**  *parameter-type-list*  **)**  /\* Neuer Deklarator \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*direct-declarator*  **(**  *identifier-list*<sub>opt</sub> **)**  /\* Veralteter Deklarator \*/

Die Parameterliste in einer Definition verwendet diese Syntax:

*parameter-type-list*: /\* Die Parameterliste \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parameter-list* <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parameter-list* **, ...**

*parameter-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parameter-declaration*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parameter-list* **,**  *parameter-declaration*

*parameter-declaration*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers* *declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers* *abstract-declarator*<sub>opt</sub>

Die Parameterliste in einer Funktionsdefinition im alten Format verwendet diese Syntax:

*identifier-list*: /\* Verwendet in veralteten Funktionsdefinitionen und Deklarationen \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier-list* **,** *identifier*

Die Syntax für den Funktionsrumpf lautet:

*compound-statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **{** *declaration-list*<sub>opt</sub> *statement-list*<sub>opt</sub> **}**

Die einzigen Speicherklassenspezifizierer, die eine Funktionsdeklaration ändern können, sind **extern** und **static**. Der Bezeichner **extern** gibt an, dass von anderen Dateien auf die Funktion verwiesen werden kann; das bedeutet, der Funktionsname wird in den Linker exportiert. Der **static**-Bezeichner gibt an, dass auf die Funktion nicht von anderen Dateien verwiesen werden kann, d.h., der Name wird nicht vom Linker exportiert. Wenn keine Speicherklasse in einer Funktionsdefinition steht, wird **extern** angenommen. In jedem Fall ist die Funktion stets vom Definitionspunkt bis an das Ende der Datei sichtbar.

Die optionalen *declaration-specifiers* und der erforderliche *declarator* geben gemeinsam den Rückgabetyp und den Namen der Funktion an. Der *declarator* ist eine Kombination aus dem Bezeichner, der die Funktion benennt, und den Klammern hinter dem Funktionsnamen. Der optionale *attribute-seq*-Nichtterminal ist eine Microsoft-spezifische Funktion, die unter [Funktionsattribute](../c-language/function-attributes.md) definiert wird.

Der *direct-declarator* (in der *declarator*-Syntax) legt den Namen der Funktion fest, die definiert wird, sowie die Bezeichner ihrer Parameter. Wenn *direct-declarator* eine *parameter-type-list* enthält, gibt die Liste die Typen aller Parameter an. Eine solche Deklaration dient auch als Funktionsprototyp für spätere Aufrufe der Funktion.

Eine *declaration* in der *declaration-list* in den Funktionsdefinitionen kann keinen *storage-class-specifier* außer **register** enthalten. Der *type-specifier* in der *declaration-specifiers*-Syntax kann nur dann weggelassen werden, wenn die **register**-Speicherklasse für einen Wert vom Typ **int** angegeben wird.

Die *compound-statement* ist der Funktionsrumpf, der lokale Variablendeklarationen, Verweise auf extern deklarierte Elemente und Anweisungen enthält.

Die Abschnitte [Funktionsattribute](../c-language/function-attributes.md), [Speicherklasse](../c-language/storage-class.md), [Rückgabetyp](../c-language/return-type.md), [Parameter](../c-language/parameters.md) und [Funktionsrumpf](../c-language/function-body.md) beschreiben die Komponenten der Funktionsdefinition im Detail.

## <a name="see-also"></a>Siehe auch

[Funktionen](../c-language/functions-c.md)
