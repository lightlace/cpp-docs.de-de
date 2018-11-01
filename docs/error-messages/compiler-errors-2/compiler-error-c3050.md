---
title: Compilerfehler C3050
ms.date: 11/04/2016
f1_keywords:
- C3050
helpviewer_keywords:
- C3050
ms.assetid: ee090a0b-29cc-4215-a2f9-d82af79b8e82
ms.openlocfilehash: 255647a2e603b5a71855374dba3248ffef1e025e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50440429"
---
# <a name="compiler-error-c3050"></a>Compilerfehler C3050

'Typ1': Eine Verweisklasse kann nicht von 'Typ1' erben.

`System::ValueType` kann keine Basisklasse für einen Verweistyp sein.

Im folgenden Beispiel wird C3050 generiert:

```
// C3050.cpp
// compile with: /clr /LD
ref struct X : System::ValueType {};   // C3050
ref struct Y {};   // OK
```