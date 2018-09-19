---
title: Compilerwarnung (Stufe 1) C4237 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4237
dev_langs:
- C++
helpviewer_keywords:
- C4237
ms.assetid: f2e86c4b-80d8-460e-9429-83c5f3f5d7ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ca72e4973c71655bc4a891570c6f686304d07eb0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092894"
---
# <a name="compiler-warning-level-1-c4237"></a>Compilerwarnung (Stufe 1) C4237

' Schlüsselwort ' wird noch nicht unterstützt, aber für zukünftige Verwendung reserviert

Ein Schlüsselwort in der C++-Spezifikation ist nicht in Visual C++-Compiler implementiert, aber das Schlüsselwort ist nicht als ein benutzerdefiniertes Symbol zur Verfügung.

Im folgende Beispiel wird die C4237 generiert:

```
// C4237.cpp
// compile with: /W1 /c
int export;   // C4237
```