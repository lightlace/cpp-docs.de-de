---
title: C-Speicherklassenattribute (erweitert)
ms.date: 11/04/2016
helpviewer_keywords:
- __declspec keyword [C]
- extended attributes
- extended storage-class attributes
- storage class specifiers, C storage classes
ms.assetid: 2580735c-f5bf-46ab-9468-0696893d82be
ms.openlocfilehash: 9b0c8b60dab3229d5d5c162f7bafc959fa2558f0
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56146956"
---
# <a name="c-extended-storage-class-attributes"></a>C-Speicherklassenattribute (erweitert)

**Microsoft-spezifisch**

Weitere aktuelle Informationen über dieses Thema finden Sie unter [__declspec (C++-Verweis)](../cpp/declspec.md).

Die erweiterte Attributsyntax vereinfacht und standardisiert Microsoft-spezifische Erweiterungen der Programmiersprache C. Zu den Speicherklassenattributen, die die erweiterte Attributsyntax verwenden, gehören Thread, naked, dllimport und dllexport.

Der erweiterte Attributsyntax zur Bezeichnung von Speicherklasseninformation verwendet das _declspec-Schlüsselwort, welches angibt, dass eine Instanz eines gegebenen Typs mit einem Microsoft-spezifischen Speicherklassenattribut (thread, naked, dllimport oder dllexport) gespeichert werden muss. Beispiele anderer Speicherklassenmodifizierer umfassen die statischen und externen Schlüsselwörter. Allerdings sind diese Schlüsselwörter Teil des ANSI C-Standards und werden somit nicht von der erweiterten Attributsyntax abgedeckt.

## <a name="syntax"></a>Syntax

*storage-class-specifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__declspec (** *extended-decl-modifier-seq* **)** /\* Microsoft-spezifisch \*/

*extended-decl-modifier-seq*:&nbsp;&nbsp;&nbsp;&nbsp;/\* Microsoft-spezifisch \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*extended-decl-modifier*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*extended-decl-modifier-seq* *extended-decl-modifier*

*extended-decl-modifier*:&nbsp;&nbsp;&nbsp;&nbsp;/\* Microsoft-spezifisch \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**thread**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**naked**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllimport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllexport**

Die Deklarationsmodifizierer sind durch Leerzeichen getrennt. Beachten Sie, dass *extended-decl-modifier-seq* leer sein darf. „__declspec“ hat in diesem Fall keine Auswirkungen.

Die Speicherklassenattribute thread, naked, dllimport und dllexport sind nur Eigenschaften für die Daten- oder Funktionsdeklaration, auf die sie angewendet werden. Sie definieren nicht die Typattribute der Funktion selbst neu. Das Threadattribut wirkt sich nur auf Daten aus. Das naked-Attribut wirkt sich nur auf Funktionen aus. Die Attribute dllimport und dllexport wirken sich auf Funktionen und Daten aus.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Deklarationen und Typen](../c-language/declarations-and-types.md)
