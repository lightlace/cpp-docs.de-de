---
title: Compilerfehler C2390
ms.date: 11/04/2016
f1_keywords:
- C2390
helpviewer_keywords:
- C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
ms.openlocfilehash: 515e2e151d27dd2eb84fc1dc71b9197b36b14cbb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745043"
---
# <a name="compiler-error-c2390"></a>Compilerfehler C2390

"Bezeichner": falsche Speicher Klasse "Spezifizierer"

Die Speicher Klasse ist für den Bezeichner des globalen Bereichs nicht gültig. Die Standard Speicher Klasse wird anstelle der ungültigen-Klasse verwendet.

Mögliche Lösungen:

- Wenn der Bezeichner eine Funktion ist, deklarieren Sie ihn mit `extern` Storage.

- Wenn der Bezeichner ein formaler Parameter oder eine lokale Variable ist, deklarieren Sie ihn mit dem automatischen Speicher.

- Wenn der Bezeichner eine globale Variable ist, deklarieren Sie ihn ohne Speicher Klasse (automatischer Speicher).

## <a name="example"></a>Beispiel

- Im folgenden Beispiel wird C2390 generiert:

```cpp
// C2390.cpp
register int i;   // C2390

int main() {
   register int j;   // OK
}
```
