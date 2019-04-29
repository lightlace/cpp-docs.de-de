---
title: Compilerfehler C2087
ms.date: 11/04/2016
f1_keywords:
- C2087
helpviewer_keywords:
- C2087
ms.assetid: 89761e83-415a-4468-a4c6-b6dedfd1dd6a
ms.openlocfilehash: 11d5a0a86ba399e28a641fa490f19be020db2d9d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301434"
---
# <a name="compiler-error-c2087"></a>Compilerfehler C2087

"Bezeichner": Feldindex fehlt

Die Definition eines Arrays mit mehreren Indizes fehlt ein Indexwert für eine Dimension, die höher als 1.

Im folgende Beispiel wird die C2087 generiert:

```
// C2087.cpp
int main() {
   char a[10][];   // C2087
}
```

Mögliche Lösung:

```
// C2087b.cpp
int main() {
   char b[4][5];
}
```