---
title: Funktionsaufrufkonvertierungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function calls, converting
- function calls, argument type conversions
- functions [C], argument conversions
ms.assetid: 04ea0f81-509a-4913-8b12-0937a81babcf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c3a1a245511f0ab849c28ab9a03ba76903609643
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065659"
---
# <a name="function-call-conversions"></a>Funktionsaufrufkonvertierungen

Der Konvertierungstyp, der an Argumenten in einem Funktionsaufruf ausgeführt wird, hängt von der Anwesenheit eines Funktionsprototyps (Vorwärtsdeklaration) mit deklarierten Argumenttypen für die aufgerufene Funktion ab.

Wenn ein Funktionsprototyp vorhanden ist und deklarierte Argumenttypen enthält, führt der Compiler die Typüberprüfung aus (siehe [Funktionen](../c-language/functions-c.md)).

Wenn kein Funktionsprototyp vorhanden ist, werden nur die üblichen arithmetischen Konvertierungen mit den Argumenten im Funktionsaufruf ausgeführt. Diese Konvertierungen werden für jedes Argument im Aufruf unabhängig ausgeführt. Dies bedeutet, dass ein **float**-Wert in einen **double**-Wert, ein `char`- oder **short**-Wert in einen `int`-Wert und ein `unsigned char`- oder **unsigned short**-Wert in einen `unsigned int`-Wert konvertiert wird.

## <a name="see-also"></a>Siehe auch

[Typkonvertierungen](../c-language/type-conversions-c.md)