---
title: Compilerfehler C2844
ms.date: 11/04/2016
f1_keywords:
- C2844
helpviewer_keywords:
- C2844
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
ms.openlocfilehash: 8af9f42be279f728f72fc6968aeba98ee5d2474a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462711"
---
# <a name="compiler-error-c2844"></a>Compilerfehler C2844

'Member': ein Member der Schnittstelle "Schnittstelle" nicht möglich

Ein [Schnittstellenklasse](../../windows/interface-class-cpp-component-extensions.md) einen Datenmember kann nicht enthalten, es sei denn, sie auch eine Eigenschaft ist.

Etwas anderes als eine Eigenschaft oder das Member-Funktion kann nicht in einer Schnittstelle. Darüber hinaus sind die Konstruktoren, Destruktoren und Operatoren nicht zulässig.

Im folgende Beispiel wird die C2844 generiert:

```
// C2844a.cpp
// compile with: /clr /c
public interface class IFace {
   int i;   // C2844
   // try the following line instead
   // property int Size;
};
```
