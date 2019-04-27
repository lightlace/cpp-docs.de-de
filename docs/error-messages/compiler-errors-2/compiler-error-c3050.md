---
title: Compilerfehler C3050
ms.date: 11/04/2016
f1_keywords:
- C3050
helpviewer_keywords:
- C3050
ms.assetid: ee090a0b-29cc-4215-a2f9-d82af79b8e82
ms.openlocfilehash: 255647a2e603b5a71855374dba3248ffef1e025e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187470"
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