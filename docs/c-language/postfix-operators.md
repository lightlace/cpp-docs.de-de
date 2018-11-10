---
title: Postfix-Operatoren
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C], postfix
- postfix operators
ms.assetid: 76260011-1624-484e-8bef-72ae7ab556cc
ms.openlocfilehash: 45f7b67b62657c498bdd9ebcf5d85379cdcdd211
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50440703"
---
# <a name="postfix-operators"></a>Postfix-Operatoren

Die Postfix-Operatoren weisen den höchsten Rang (die festeste Bindung) in der Ausdrucksauswertung auf.

## <a name="syntax"></a>Syntax

*postfix-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*primary-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **[**  *expression*  **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **(**  *argument-expression-list*<sub>opt</sub> **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **.**  *identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **->**  *identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **++**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **--**

Operatoren in dieser Rangfolgenebene sind die Arrayfeldindizes, Funktionsaufrufe, die Struktur- und Union-Member sowie Postfix-Operatoren für Inkrement und Dekrement.

## <a name="see-also"></a>Siehe auch

[C-Operatoren](../c-language/c-operators.md)