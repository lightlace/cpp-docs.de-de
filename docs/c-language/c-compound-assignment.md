---
title: C-Verbundzuweisung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C], assignment
- compound assignment operators
- assignment operators, compound
ms.assetid: db7b5893-cd56-4f1c-9981-5a024200ab63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1c4450682abbb5efd739b5eb08d228b4c55d00ec
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029324"
---
# <a name="c-compound-assignment"></a>C-Verbundzuweisung

Die Verbundzuweisungsoperatoren kombinieren den Einfachzuweisungsoperator mit einem anderen binären Operator. Verbundzuweisungsoperatoren führen einen Vorgang aus, der vom zusätzlichen Operator angegeben wurde, und weisen das Ergebnis dann dem linken Operanden zu. Zum Beispiel kann ein Verbundzuweisungsausdruck wie

> *expression1* **+=** *expression2*

verstanden werden als

> *expression1* **=** *expression1* **+** *expression2*

Allerdings ist der Verbundzuweisungsausdruck nicht mit der erweiterten Version äquivalent, da der Verbundzuweisungsausdruck *expression1* nur einmal auswertet, während die erweiterte Version *expression1* zweimal auswertet: in der Additions- und in der Zuweisungsoperation.

Die Operanden des Verbundzuweisungsoperators müssen vom Typ „Ganzzahl“ oder „Gleitkomma“ sein. Jeder Verbundzuweisungsoperator führt die Konvertierungen aus, die der entsprechende binäre Operator ausführt, und schränkt die Typen seiner Operanden entsprechend ein. Die Operatoren für die Additionszuweisung (`+=`) und die Subtraktionszuweisung (**-=**) können über einen linken Operanden vom Zeigertyp verfügen. In diesem Fall muss der rechte Operand integralen Typs sein. Das Ergebnis eines Verbundzuweisungsvorgangs hat den Wert und Typ des linken Operanden.

```C
#define MASK 0xff00

n &= MASK;
```

In diesem Beispiel wird ein bitweiser inklusiver AND-Vorgang für `n` und `MASK` ausgeführt, und das Ergebnis wird `n` zugewiesen. Die Manifestkonstante `MASK` wird mit einer [#define](../preprocessor/hash-define-directive-c-cpp.md)-Präprozessoranweisung definiert.

## <a name="see-also"></a>Siehe auch

[C-Zuweisungsoperatoren](../c-language/c-assignment-operators.md)