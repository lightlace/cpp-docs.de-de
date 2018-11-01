---
title: Compilerfehler C2870
ms.date: 11/04/2016
f1_keywords:
- C2870
helpviewer_keywords:
- C2870
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
ms.openlocfilehash: f61281da23e46236e7fce496a4d89086e5d6c0ea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50546369"
---
# <a name="compiler-error-c2870"></a>Compilerfehler C2870

'Name': eine Namespace-Definition muss entweder im Dateigültigkeitsbereich oder unmittelbar in einem anderen Namespace-Definition angezeigt werden

Sie definiert Namespace `name` falsch. Namespaces muss definiert werden, im Dateigültigkeitsbereich (außerhalb aller Blöcke und Klassen) oder direkt in einen anderen Namespace.

Im folgende Beispiel wird die C2870 generiert:

```
// C2870.cpp
// compile with: /c
int main() {
   namespace A { int i; };   // C2870
}
```