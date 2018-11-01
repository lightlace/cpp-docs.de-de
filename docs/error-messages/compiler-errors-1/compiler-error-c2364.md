---
title: Compilerfehler C2364
ms.date: 11/04/2016
f1_keywords:
- C2364
helpviewer_keywords:
- C2364
ms.assetid: 4f550571-94b5-42ca-84cb-663fecbead44
ms.openlocfilehash: 051468ea861190dd3f6a28dc272f1bab155145af
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558898"
---
# <a name="compiler-error-c2364"></a>Compilerfehler C2364

'Typ': Unzulässiger Typ für das benutzerdefinierte Attribut

Benannte Argumente für benutzerdefinierte Attribute sind zum Kompilieren von Konstanten zur beschränkt. Z. B. ganzzahligen Typen (Int, Char, usw.), System:: Type ^, und das System:: Object ^.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2364 generiert.

```
// c2364.cpp
// compile with: /clr /c
using namespace System;

[attribute(AttributeTargets::All)]
public ref struct ABC {
public:
   // Delete the following line to resolve.
   ABC( Enum^ ) {}   // C2364
   ABC( int ) {}   // OK
};
```