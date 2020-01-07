---
title: Compilerfehler C2054
ms.date: 11/04/2016
f1_keywords:
- C2054
helpviewer_keywords:
- C2054
ms.assetid: 37f7c612-0d7d-4728-9e67-ac4160555f48
ms.openlocfilehash: e7d90d684c1d95f540f6357bf61ee7c6f889ad3f
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302054"
---
# <a name="compiler-error-c2054"></a>Compilerfehler C2054

erwartet wurde "(" für "Identifier".

Der Funktions Bezeichner wird in einem Kontext verwendet, der nachfolgende Klammern erfordert.

Dieser Fehler kann dadurch verursacht werden, dass bei einer komplexen Initialisierung ein Gleichheitszeichen (=) weggelassen wird.

Im folgenden Beispiel wird C2054 generiert:

```c
// C2054.c
int array1[] { 1, 2, 3 };   // C2054, missing =
```

Mögliche Lösung:

```c
// C2054b.c
int main() {
   int array2[] = { 1, 2, 3 };
}
```
