---
title: Compilerfehler C3247
ms.date: 11/04/2016
f1_keywords:
- C3247
helpviewer_keywords:
- C3247
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
ms.openlocfilehash: 81dc5d5e54551aff49adad2ada2eb25f57a37ec2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754380"
---
# <a name="compiler-error-c3247"></a>Compilerfehler C3247

'Klasse1': Eine Co-Klasse kann nicht von einer anderen Co-Klasse 'Klasse2' erben.

Eine Klasse mit dem [coclass](../../windows/coclass.md) -Attribut gekennzeichnete Klasse kann nicht von einer anderen Klasse erben, die mit dem `coclass` -Attribut markiert ist.

Im folgenden Beispiel wird C3247 generiert:

```cpp
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
