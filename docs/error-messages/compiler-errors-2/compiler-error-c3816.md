---
title: Compilerfehler C3816 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3816
dev_langs:
- C++
helpviewer_keywords:
- C3816
ms.assetid: 2e52cc7f-e31c-41a3-8d6f-9f5fab3648c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bfc0cf864caeefd5b19e3d40383724909575d4df
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115891"
---
# <a name="compiler-error-c3816"></a>Compilerfehler C3816

'Declaration' wurde bereits deklariert oder definiert, die mit einem anderen verwalteten oder WinRTmodifier

Für eine Vorwärts- und eine tatsächliche Deklaration ist es erforderlich, dass in der Deklaration der Attribute keine Konflikte oder Inkonsistenzen vorliegen.

Im folgenden Beispiel wird C3816 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C3816a.cpp
// compile with: /clr /c
class C1;
// try the following line instead
// ref class C1;

ref class C1{  // C3816, forward declaration does not use ref
};
```