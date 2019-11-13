---
title: Compilerwarnung (Stufe 1) C4659
ms.date: 11/04/2016
f1_keywords:
- C4659
helpviewer_keywords:
- C4659
ms.assetid: e29ba8db-7917-43f6-8e34-868b752279ae
ms.openlocfilehash: 27023e6886638be63db1e1fb654c0caa70769a56
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052530"
---
# <a name="compiler-warning-level-1-c4659"></a>Compilerwarnung (Stufe 1) C4659

\#Pragma ' pragma ': die Verwendung des reservierten Segments ' Segment ' weist ein undefiniertes Verhalten auf. verwenden Sie #pragma Kommentar (linker,...).

Die Option. drectve wurde verwendet, um eine Option an den Linker zu übergeben. Verwenden Sie stattdessen Pragma [comment](../../preprocessor/comment-c-cpp.md) zum Übergeben einer Linkeroption.

```cpp
// C4659.cpp
// compile with: /W1 /LD
#pragma code_seg(".drectve")   // C4659
```