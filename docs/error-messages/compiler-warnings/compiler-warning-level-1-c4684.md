---
title: Compilerwarnung (Stufe 1) C4684
ms.date: 11/04/2016
f1_keywords:
- C4684
helpviewer_keywords:
- C4684
ms.assetid: e95f1a83-2784-4b05-ae94-12148e056e26
ms.openlocfilehash: 8ba3d75ecb370ac86c9a6ab47f05dd49fc12ba23
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374403"
---
# <a name="compiler-warning-level-1-c4684"></a>Compilerwarnung (Stufe 1) C4684

'Attribut': WARNUNG!! Attribut kann zu Ungültiger codegenerierung führen: Verwenden Sie mit Vorsicht

Sie verwendet ein Attribut, das nicht häufig verwendet werden soll.

Im folgende Beispiel wird die C4684 generiert:

```
// C4684.cpp
// compile with: /W1 /LD
[module(name="xx")]; // C4684 expected
[no_injected_text];
```