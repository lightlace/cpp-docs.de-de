---
title: Compilerwarnung (Stufe 1) C4659 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4659
dev_langs:
- C++
helpviewer_keywords:
- C4659
ms.assetid: e29ba8db-7917-43f6-8e34-868b752279ae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d00c54fa77d68722b2e47a9d49832911b398deca
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110056"
---
# <a name="compiler-warning-level-1-c4659"></a>Compilerwarnung (Stufe 1) C4659

\#Pragma "Pragma": Gebrauch des reservierten Segments "Segment" hat ein undefiniertes Verhalten, verwenden Sie #pragma Comment (Linker,...)

Die Option .drectve wurde verwendet, um eine Option für dem Linker übergeben. Verwenden Sie stattdessen Pragma [Kommentar](../../preprocessor/comment-c-cpp.md) für die Übergabe einer Linkeroption.

```
// C4659.cpp
// compile with: /W1 /LD
#pragma code_seg(".drectve")   // C4659
```