---
title: Compilerfehler C3769 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3769
dev_langs:
- C++
helpviewer_keywords:
- C3769
ms.assetid: 341675e1-7428-4da6-8275-1b2f0a70dacc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da57a883bcf66535a531e98e23b5927d37cadccd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042226"
---
# <a name="compiler-error-c3769"></a>Compilerfehler C3769

'Typ': eine geschachtelte Klasse kann nicht den gleichen Namen wie die Sie unmittelbar umschließende Klasse aufweisen

Eine geschachtelte Klasse kann nicht den gleichen Namen wie die Sie unmittelbar umschließende Klasse aufweisen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3769 generiert.

```
// C3769.cpp
// compile with: /c
class x {
   class x {};   // C3769
   class y {
      class x{};   // OK
   };
};
```