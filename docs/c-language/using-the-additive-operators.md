---
title: Verwenden von additiven Operatoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], addition
- additive operators
ms.assetid: 7d54841e-436d-4ae8-9865-1ac1829e6f22
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 050db08d00d79e3cfee0ab7549532d78a51b1ade
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078867"
---
# <a name="using-the-additive-operators"></a>Verwenden von additiven Operatoren

Die folgenden Beispiele, welche die Additions- und Subtraktionsoperatoren veranschaulichen, verwenden diese Deklarationen:

```
int i = 4, j;
float x[10];
float *px;
```

Diese Anweisungen sind gleichwertig:

```
px = &x[4 + i];
px = &x[4] + i;
```

Der Wert von `i` wird mit der Länge eines **float** multipliziert und zu `&x[4]` hinzugefügt. Das Zeigerwertergebnis ist die Adresse von `x[8]`.

```
j = &x[i] - &x[i-2];
```

In diesem Beispiel wird die Adresse des dritten Elements von `x` (angegeben durch `x[i-2]`) von der Adresse des fünften Elements von `x` (angegeben durch `x[i]`) subtrahiert. Die Differenz wird durch die Länge eines **float** geteilt. Das Ergebnis ist der Ganzzahlwert 2.

## <a name="see-also"></a>Siehe auch

[C-Operatoren (additiv)](../c-language/c-additive-operators.md)