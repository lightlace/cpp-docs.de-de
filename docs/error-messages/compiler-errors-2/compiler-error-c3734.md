---
title: Compilerfehler C3734 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3734
dev_langs:
- C++
helpviewer_keywords:
- C3734
ms.assetid: 4e2afdcc-7da9-45a1-9c96-85f25e2986e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d304b3853986b54f9844f9e4968f7bb7d6a8af5a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072744"
---
# <a name="compiler-error-c3734"></a>Compilerfehler C3734

„Klasse“: Eine verwaltete oder WinRT-Klasse kann kein „Co-Klasse“-Attribut sein.

Die [Co-Klasse](../../windows/coclass.md) Attribut kann nicht verwendet werden, mit verwalteten oder WinRT-Klassen.

Im folgenden Beispiel wird C3734 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C3734.cpp
// compile with: /clr /c
[module(name="x")];

[coclass]
ref class CMyClass {   // C3734 remove the ref keyword to resolve
};
```
