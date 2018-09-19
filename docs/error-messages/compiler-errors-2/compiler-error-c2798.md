---
title: Compilerfehler C2798 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2798
dev_langs:
- C++
helpviewer_keywords:
- C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 88241989d54e1a068b226b59091a381f531dee9e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028856"
---
# <a name="compiler-error-c2798"></a>Compilerfehler C2798

'super:: Member' ist mehrdeutig

Mehrere geerbte Strukturen enthalten den Member, die Sie verweist auf [super](../../cpp/super.md). Sie können den Fehler beheben, indem Sie entweder:

- Entfernen aus der Vererbungsliste von D. B1 oder B2

- Ändern den Namen des Datenelements in B1 oder B2.

Im folgende Beispiel wird die C2798 generiert:

```
// C2798.cpp
struct B1 {
   int i;
};

struct B2 {
   int i;
};

struct D : B1, B2 {
   void g() {
      __super::i = 4; // C2798
   }
};
```