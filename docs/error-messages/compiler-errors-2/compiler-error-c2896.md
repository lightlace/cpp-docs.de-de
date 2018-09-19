---
title: Compilerfehler C2896 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2896
dev_langs:
- C++
helpviewer_keywords:
- C2896
ms.assetid: b600407b-cb05-42e3-9069-2aa6960f0eaa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7cd60c4b5d1046c0b5a828539ebd66036b7cf40c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042857"
---
# <a name="compiler-error-c2896"></a>Compilerfehler C2896

"Funktion1": Verwenden Sie Funktion Vorlage "Funktion2" kann nicht als Argument

Eine Funktionsvorlage darf nicht das Argument an eine andere Funktionsvorlage sein.

Im folgende Beispiel wird die C2896 generiert:

```
// C2896.cpp
template<class T1, class T2> void f1(void(*)(T1, T2));
template<class T1, class T2> void f2(T1, T2);

int main() {
   f1(f2);   // C2896
}
```

C2896 kann auch auftreten, wenn Generika verwendet werden:

```
// C2896b.cpp
// compile with: /clr
generic<class T1> void gf1(T1){}
generic<class T1> void gf2(T1){}

int main() {
   gf1(gf2);   // C2896
   gf1(1);   // OK
}
```