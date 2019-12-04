---
title: Compilerfehler C2433
ms.date: 11/04/2016
f1_keywords:
- C2433
helpviewer_keywords:
- C2433
ms.assetid: 7079fedd-6059-4125-82ef-ebe275f1f9d1
ms.openlocfilehash: 9edb30e574e212bd30fd60dd3ce5aaddc650dc11
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744432"
---
# <a name="compiler-error-c2433"></a>Compilerfehler C2433

' Identifier ': ' Modifizierer ' ist für Datendeklarationen nicht zulässig.

Die `friend`, `virtual`und `inline` modifiziererer können nicht für Datendeklarationen verwendet werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2433 generiert.

```cpp
// C2433.cpp
class C{};

int main() {
   inline C c;   // C2433
}
```
