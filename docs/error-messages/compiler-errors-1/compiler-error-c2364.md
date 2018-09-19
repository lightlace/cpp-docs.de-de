---
title: Compilerfehler C2364 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2364
dev_langs:
- C++
helpviewer_keywords:
- C2364
ms.assetid: 4f550571-94b5-42ca-84cb-663fecbead44
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d35701eb47bdf633377652094b847ccdfb31e59
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100629"
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