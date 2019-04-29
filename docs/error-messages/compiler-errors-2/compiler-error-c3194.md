---
title: Compilerfehler C3194
ms.date: 11/04/2016
f1_keywords:
- C3194
helpviewer_keywords:
- C3194
ms.assetid: 49d3ffc6-eff6-4b46-865b-18811692a8bb
ms.openlocfilehash: 181a18dde45c3363f1f77bc0cbbd5b0ffca3e898
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397457"
---
# <a name="compiler-error-c3194"></a>Compilerfehler C3194

'Member': ein Werttyp kann nicht keinen Zuweisungsoperator aufweisen

Spezielle Memberfunktionen, die automatischen Aufruf durch den Compiler an, wie z. B. ein Kopierkonstruktor oder kopierzuordnungsoperator erfordern, werden in einer Wertklasse nicht unterstützt.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3194 generiert.

```
// C3194.cpp
// compile with: /clr /c
value struct MyStruct {
   MyStruct& operator= (const MyStruct& i) { return *this; }   // C3194
};

ref struct MyStruct2 {
   MyStruct2% operator= (const MyStruct2% i) { return *this; }   // OK
};
```