---
title: Compilerfehler C2390 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2390
dev_langs:
- C++
helpviewer_keywords:
- C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5de5a9af8f8aa04219f0a7d61162336745fd4bfa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098212"
---
# <a name="compiler-error-c2390"></a>Compilerfehler C2390

'Bezeichner': 'Spezifizierer' ist eine inkorrekte Speicherklasse

Die Speicherklasse gilt nicht für die Bezeichner im globalen Gültigkeitsbereich. Anstelle der ungültige Klasse ist die Standardspeicherklasse dient.

Mögliche Lösungen:

- Wenn der Bezeichner einer Funktion ist, deklarieren Sie ihn mit `extern` Speicher.

- Wenn der Bezeichner ein formaler Parameter oder lokale Variable ist, deklarieren Sie es mit automatischem Speicher ein.

- Wenn der Bezeichner eine globale Variable ist, deklarieren Sie ihn mit keine Speicherklasse (Auto-Speicher) ein.

## <a name="example"></a>Beispiel

- Im folgende Beispiel wird die C2390 generiert:

```
// C2390.cpp
register int i;   // C2390

int main() {
   register int j;   // OK
}
```