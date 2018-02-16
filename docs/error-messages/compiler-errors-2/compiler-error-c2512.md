---
title: Compilerfehler C2512 | Microsoft Docs
ms.custom: 
ms.date: 02/09/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2512
dev_langs:
- C++
helpviewer_keywords:
- C2512
ms.assetid: 15206da9-1164-451a-b869-280e00711aad
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 57dbb542eee7e893253e6c3bdd3410c605a8d2db
ms.sourcegitcommit: 8ae12a602244a5853e941e5e8806e3545d876844
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2018
---
# <a name="compiler-error-c2512"></a>Compilerfehler C2512

> "*Bezeichner*': kein geeigneter Standardkonstruktor verfügbar  

Ein *Standardkonstruktor*, ein Konstruktor, der keine Argumente erfordert ist nicht verfügbar für die angegebene Klasse, Struktur oder Union. Nur, wenn keine benutzerdefinierten Konstruktoren bereitgestellt werden, stellt der Compiler einen Standardkonstruktor bereit.

Wenn Sie einen Konstruktor, der einen Parameter nicht "void" akzeptiert, und Ihre Klasse ohne Parameter (z. B. die Elemente eines Arrays) erstellt werden sollen, müssen Sie auch einen Standardkonstruktor bereitstellen. Beim standardmäßigen Konstruktor kann es sich um einen Konstruktor mit standardmäßigen Werten für alle Parameter handeln.

## <a name="example"></a>Beispiel

Eine häufige Ursache für Fehler C2512 ist, wenn Sie einen Konstruktor Klasse oder Struktur definieren, der Argumente akzeptiert, und dann versuchen, eine Instanz der Klasse oder Struktur ohne Argumente deklarieren. Beispielsweise `struct B` unten deklariert einen Konstruktor, der erfordert eine `char *` Argument, aber keiner, die keine Argumente akzeptiert. In `main`, eine Instanz von B ist deklariert, aber kein Argument angegeben ist. Wenn sie einen Standardkonstruktor für b finden kann, generiert der Compiler C2512

```cpp
// C2512.cpp
// Compile with: cl /W4 c2512.cpp
// C2512 expected
struct B {
   B (char *) {}
   // Uncomment the following line to fix.
   // B() {}
};

int main() {
   B b;   // C2512 - This requires a default constructor
}
```

Sie können dieses Problem beheben, indem Sie einen Standardkonstruktor für die Struktur oder Klasse, wie z. B. definieren `B() {}`, oder einen Konstruktor, in dem alle Argumente über Standardwerte, z. B. `B (char * = nullptr) {}`.
