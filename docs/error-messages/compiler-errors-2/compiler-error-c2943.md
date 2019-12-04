---
title: Compilerfehler C2943
ms.date: 11/04/2016
f1_keywords:
- C2943
helpviewer_keywords:
- C2943
ms.assetid: ede6565e-d892-44c0-8eee-c69545f3be2e
ms.openlocfilehash: ac704c06ac0e455cccdb2b035d0947ae9ec04bd5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755394"
---
# <a name="compiler-error-c2943"></a>Compilerfehler C2943

'Klasse': 'Typ-Klasse-ID' wird als Typargument einer Vorlage neu definiert.

Eine generische oder Vorlagenklasse kann nicht anstelle eines Symbols als generisches oder Vorlagentypargument verwendet werden.

Im folgenden Beispiel wird C2943 generiert.

```cpp
// C2943.cpp
// compile with: /c
template<class T>
class List {};

template<class List<int> > class MyList;   // C2943
template<class T >  class MyList;
```
