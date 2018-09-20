---
title: Funktionsrumpf | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- functions [C], syntax
- variables, function syntax
- function definitions, function body
- function body
ms.assetid: f7e74822-fac8-4dc8-8f3a-2b1611da4640
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d30cb5429ebee0738aa7b7aab367d79867e92047
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757818"
---
# <a name="function-body"></a>Funktionsrumpf

Ein *Funktionsrumpf* entspricht einer Verbundanweisung mit den Anweisungen, die die Aufgabe der Funktion angeben.

## <a name="syntax"></a>Syntax

*function-definition*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers*<sub>opt</sub> *attribute-seq*<sub>opt</sub> *declarator* *declaration-list*<sub>opt</sub> *compound-statement*

/\* *attribute-seq* ist Microsoft-spezifisch \*/

*compound-statement*: /\* Der Funktionsrumpf \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**{** *declaration-list*<sub>opt</sub> *statement-list*<sub>opt</sub> **}**

Variablen, die in einem Funktionsrumpf deklariert werden, sogenannte *lokale Variablen*, weisen die **auto**-Speicherklasse auf, sofern nicht anders angegeben. Wenn die Funktion aufgerufen wird, wird Speicherplatz für die lokalen Variablen erstellt, und lokale Initialisierungen werden ausgeführt. Die Ausführungssteuerung wird an die erste Anweisung in *compound-statement* übergeben und fährt fort, bis eine **return**-Anweisung ausgeführt wurde oder das Ende des Funktionsrumpfs erreicht ist. Anschließend wird die Steuerung wieder an den Punkt zurückgegeben, an dem die Funktion aufgerufen wurde.

Eine **return**-Anweisung, die einen Ausdruck enthält, muss ausgeführt werden, wenn die Funktion einen Wert zurückgeben soll. Der Rückgabewert einer Funktion ist nicht definiert, wenn keine **return**-Anweisung ausgeführt wird, oder wenn die **return**-Anweisung keinen Ausdruck enthält.

## <a name="see-also"></a>Siehe auch

[C-Funktionsdefinitionen](../c-language/c-function-definitions.md)