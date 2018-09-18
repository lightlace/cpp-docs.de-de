---
title: Compilerfehler C2626 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2626
dev_langs:
- C++
helpviewer_keywords:
- C2626
ms.assetid: 4c283ad0-251b-4571-bc18-468b9836746f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9929da1f0cf9ffd9c70048017fdef1d854c1fcc9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074681"
---
# <a name="compiler-error-c2626"></a>Compilerfehler C2626

'identifier': Ein privates oder geschütztes Datenmember ist in einer anonymen Struktur oder Union nicht zulässig.

Ein Member einer anonymen Struktur oder Union muss über öffentlichen Zugriff verfügen.

Im folgenden Beispiel wird C2626 generiert:

```
// C2626.cpp
int main() {
   union {
   protected:
      int j;     // C2626, j is protected
   private:
      int k;     // C2626, k is private
   };
}
```

Entfernen Sie zum Beheben dieses Problems private oder geschützte Tags:

```
// C2626b.cpp
int main() {
   union {
   public:
      int i;   // OK, i is public
   };
}
```