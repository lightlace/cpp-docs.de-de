---
title: Compilerfehler C2094 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2094
dev_langs:
- C++
helpviewer_keywords:
- C2094
ms.assetid: 9e4f8f88-f189-46e7-91c9-481bacc7af87
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e3591fef423bc24562a2f2edf18f7f2774cfcc4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46073524"
---
# <a name="compiler-error-c2094"></a>Compilerfehler C2094

Bezeichnung "identifier" nicht definiert

Die von einer [goto](../../cpp/goto-statement-cpp.md) -Anweisung verwendete Bezeichnung ist in der Funktion nicht vorhanden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2094 generiert:

```cpp
// C2094.c
int main() {
   goto test;
}   // C2094
```

Mögliche Lösung:

```cpp
// C2094b.c
int main() {
   goto test;
   test:
   {
   }
}
```