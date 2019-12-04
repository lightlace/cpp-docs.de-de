---
title: Compilerfehler C2736
ms.date: 11/04/2016
f1_keywords:
- C2736
helpviewer_keywords:
- C2736
ms.assetid: 95a6bc28-c0cb-49dc-87e6-e993dbbba881
ms.openlocfilehash: 6a7781ebcd7cefdbcff13599912c06062f20501e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759684"
---
# <a name="compiler-error-c2736"></a>Compilerfehler C2736

Das Schlüsselwort "Keyword" ist in CAST nicht zulässig.

Das Schlüsselwort ist in einer Umwandlung ungültig.

Im folgenden Beispiel wird C2736 generiert:

```cpp
// C2736.cpp
int main() {
   return (virtual) 0;   // C2736
   // try the following line instead
   // return 0;
}
```
