---
title: Compilerfehler C3247 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3247
dev_langs:
- C++
helpviewer_keywords:
- C3247
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f706b4f1a1935a5c6246ea285c7e8b2b746f08cb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047238"
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