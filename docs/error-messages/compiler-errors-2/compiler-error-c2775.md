---
title: Compilerfehler C2775 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2775
dev_langs:
- C++
helpviewer_keywords:
- C2775
ms.assetid: 9c488508-ade0-48f1-b94f-d538d15f807a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c5a3031fede7b2f47510f80eba09f62a06343f7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045834"
---
# <a name="compiler-error-c2775"></a>Compilerfehler C2775

'Bezeichner': kein 'get'-Methode ist mit dieser Eigenschaft verbunden

Ein Datenmember deklariert, mit der [Eigenschaft](../../cpp/property-cpp.md) erweitertes Attribut verfügt nicht über eine `get` -Funktion angegeben, aber ein Ausdruck versucht, dessen Wert abgerufen.

Im folgende Beispiel wird die C2775 generiert:

```
// C2775.cpp
struct A {
   __declspec(property(put=PutProp2, get=GetProp2)) int prop2;
   int GetProp2(){return 0;}
   void PutProp2(int){}

   __declspec(property(put=PutProp)) int prop;
   int PutProp(void){}

};

int main() {
   A* pa = new A;
   int x;
   x = pa->prop;   // C2775
   x = pa->prop2;
}
```