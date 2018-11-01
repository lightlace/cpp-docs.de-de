---
title: Compilerwarnung (Stufe 1) C4632
ms.date: 11/04/2016
f1_keywords:
- C4632
helpviewer_keywords:
- C4632
ms.assetid: 9e35d205-cf21-4e34-8bd5-e1e7b0e2cdd3
ms.openlocfilehash: f1870da4f7889d79f5a4eabfcc3a95a21703e9fd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605412"
---
# <a name="compiler-warning-level-1-c4632"></a>Compilerwarnung (Stufe 1) C4632

Der XML-Dokumentkommentar: Datei - Zugriff verweigert: Grund

Der Pfad zu XDC-Datei (`file`) war ungültig, und keine XDC-Datei erstellt.

Im folgende Beispiel wird die C4632 generiert:

```
// C4632.cpp
// compile with: /clr /docv:\\falsedir /LD /W1
// C4632 expected

/// Text for class MyClass.
public ref class MyClass {};
```