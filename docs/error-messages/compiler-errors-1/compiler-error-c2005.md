---
title: Compilerfehler C2005 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2005
dev_langs:
- C++
helpviewer_keywords:
- C2005
ms.assetid: 090530ed-e0ec-4358-833a-ca24260e7ffe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6dfba3b960a046bf40751c135c3b99fbe843545
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100671"
---
# <a name="compiler-error-c2005"></a>Compilerfehler C2005

\#Zeile erwartet eine Zeilennummer 'token' gefunden

Die `#line` Richtlinie muss die Nummer einer Zeile folgen.

Im folgende Beispiel wird die C2005 generiert:

```
// C2005.cpp
int main() {
   int i = 0;
   #line i   // C2005
}
```

Mögliche Lösung:

```
// C2005b.cpp
int main() {
   int i = 0;
   #line 0
}
```