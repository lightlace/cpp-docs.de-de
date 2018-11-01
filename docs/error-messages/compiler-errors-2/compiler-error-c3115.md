---
title: Compilerfehler C3115
ms.date: 11/04/2016
f1_keywords:
- C3115
helpviewer_keywords:
- C3115
ms.assetid: 51726145-9782-4ec9-84b9-286f366d9cbd
ms.openlocfilehash: e334836986548d4f854dd9a5760bd8315b769d03
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50520496"
---
# <a name="compiler-error-c3115"></a>Compilerfehler C3115

'Attribut': Dieses Attribut ist für 'Konstrukt' unzulässig

Ein Attribut wurde für ein Konstrukt angewendet, für die sie nicht bestimmt ist.  Finden Sie unter [Attribute nach Verwendung](../../windows/attributes/attributes-by-usage.md) für Weitere Informationen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3115 generiert.

```
// C3115.cpp
// compile with: /c
#include <unknwn.h>
[module(name="xx")];

[object, helpstringdll(xx.dll), uuid("00000000-0000-0000-0000-000000000001")]   // C3115
// try the following line instead
// [object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI {
   HRESULT xx();
};
```