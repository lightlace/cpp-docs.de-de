---
title: Compilerfehler C3247
ms.date: 11/04/2016
f1_keywords:
- C3247
helpviewer_keywords:
- C3247
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
ms.openlocfilehash: 7ca84b4f054852aefa75a9c4547286137b436c63
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569162"
---
# <a name="compiler-error-c3247"></a>Compilerfehler C3247

'Klasse1': Eine Co-Klasse kann nicht von einer anderen Co-Klasse 'Klasse2' erben.

Eine Klasse mit dem [coclass](../../windows/coclass.md) -Attribut gekennzeichnete Klasse kann nicht von einer anderen Klasse erben, die mit dem `coclass` -Attribut markiert ist.

Im folgenden Beispiel wird C3247 generiert:

```
// C3247.cpp
[module(name="MyLib")];
[coclass]
class a {
};

[coclass]
class b : public a {   // C3247
};
int main() {
}
```