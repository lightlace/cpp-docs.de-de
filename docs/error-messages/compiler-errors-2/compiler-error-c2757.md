---
title: Compilerfehler C2757
ms.date: 11/04/2016
f1_keywords:
- C2757
helpviewer_keywords:
- C2757
ms.assetid: 421f102f-8a32-4d47-a109-811ddf2c909d
ms.openlocfilehash: 98b43a2f3c0888fc385226cd80889b9911c84690
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227912"
---
# <a name="compiler-error-c2757"></a>Compilerfehler C2757

'Symbol': ein Symbol mit diesem Namen bereits vorhanden ist und daher diesen Namen nicht als ein Namespacename verwendet werden

Ein Symbol in der aktuellen Kompilierung verwendet werden, wie Sie ein Namespace-Bezeichner in einer referenzierten Assembly bereits verwendet wird.

Im folgende Beispiel wird die C2757 generiert:

```
// C2757a.cpp
// compile with: /clr /LD
public ref class Nes {};
```

und anschließend

```
// C2757b.cpp
// compile with: /clr /c
#using <C2757a.dll>

namespace Nes {    // C2757
// try the following line instead
// namespace Nes2 {
   public ref class X {};
}
```
