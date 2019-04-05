---
title: Compilerfehler C2844
ms.date: 11/04/2016
f1_keywords:
- C2844
helpviewer_keywords:
- C2844
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
ms.openlocfilehash: 2676a32cee487595a2241359496ae9b0380126b8
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58775010"
---
# <a name="compiler-error-c2844"></a>Compilerfehler C2844

'Member': ein Member der Schnittstelle "Schnittstelle" nicht möglich

Ein [Schnittstellenklasse](../../extensions/interface-class-cpp-component-extensions.md) einen Datenmember kann nicht enthalten, es sei denn, sie auch eine Eigenschaft ist.

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
