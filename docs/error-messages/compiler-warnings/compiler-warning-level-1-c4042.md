---
title: Compilerwarnung (Stufe 1) C4042 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4042
dev_langs:
- C++
helpviewer_keywords:
- C4042
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5bef2071cf31123b5b172df2651c0d6a6d87d4fc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067471"
---
# <a name="compiler-warning-level-1-c4042"></a>Compilerwarnung (Stufe 1) C4042

'Bezeichner': besitzt unzulässige Speicherklasse

Die angegebene Speicher-Klasse kann nicht mit der folgenden ID in diesem Kontext nicht verwendet werden. Der Compiler verwendet die Speicherklasse standardmäßig stattdessen:

- `extern`, wenn *Bezeichner* ist eine Funktion.

- **automatische**, wenn *Bezeichner* ist eine formale Parameter oder lokale Variable.

- Klasse, wenn kein Speicher *Bezeichner* ist eine globale Variable.

Diese Warnung kann verursacht werden, außer mit einer Speicherklasse **registrieren** in einer Parameterdeklaration.

Das folgende Beispiel generiert C4042

```
// C4042.cpp
// compile with: /W1 /LD
int func2( __declspec( thread ) int tls_i )    // C4042
// try the following line instead
// int func2( int tls_i )
{
   return tls_i;
}
```