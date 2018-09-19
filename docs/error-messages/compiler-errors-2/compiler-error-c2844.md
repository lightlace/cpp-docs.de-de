---
title: Compilerfehler C2844 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2844
dev_langs:
- C++
helpviewer_keywords:
- C2844
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5dd4cbdc30523563207fe2a66c1c5cb158f84c94
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092101"
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
