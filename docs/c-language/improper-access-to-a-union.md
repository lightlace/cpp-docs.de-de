---
title: Unsachgemäßer Zugriff auf eine Union | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: b273d984-62a8-4003-9a87-bf0149d3f2dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2ac723ed80eaebc4b3f245ef56b761600007cd2d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028375"
---
# <a name="improper-access-to-a-union"></a>Unsachgemäßer Zugriff auf eine Union

**ANSI 3.3.2.3** Auf ein Member eines union-Objekts wird mithilfe eines Members eines anderen Typs zugegriffen

Wenn eine Union von zwei Typen deklariert wird und ein Wert gespeichert ist, aber mit dem anderen Typ auf die Union zugegriffen wird, sind die Ergebnisse unzuverlässig.

Beispielsweise wird eine Union von **float** und `int` deklariert. Ein **float**-Wert wird gespeichert, aber später greift das Programm auf den Wert als `int` zu. In einer solchen Situation ist der Wert der internen Speicherung von **float**-Werten abhängig. Der Ganzzahlwert wäre nicht zuverlässig.

## <a name="see-also"></a>Siehe auch

[Strukturen, Unions, Enumerationen und Bitfelder](../c-language/structures-unions-enumerations-and-bit-fields.md)