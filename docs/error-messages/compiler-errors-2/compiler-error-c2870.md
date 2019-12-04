---
title: Compilerfehler C2870
ms.date: 11/04/2016
f1_keywords:
- C2870
helpviewer_keywords:
- C2870
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
ms.openlocfilehash: 3b006592723df1222d05e39b3bc9e5729efc8aa6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755030"
---
# <a name="compiler-error-c2870"></a>Compilerfehler C2870

"Name": eine Namespace Definition muss entweder im Datei Gültigkeitsbereich oder unmittelbar in einer anderen Namespace Definition angezeigt werden.

Der Namespace wurde `name` falsch definiert. Namespaces müssen im Datei Gültigkeitsbereich (außerhalb aller Blöcke und Klassen) oder direkt in einem anderen Namespace definiert werden.

Im folgenden Beispiel wird C2870 generiert:

```cpp
// C2870.cpp
// compile with: /c
int main() {
   namespace A { int i; };   // C2870
}
```
