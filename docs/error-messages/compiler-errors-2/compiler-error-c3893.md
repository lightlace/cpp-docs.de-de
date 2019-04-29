---
title: Compilerfehler C3893
ms.date: 11/04/2016
f1_keywords:
- C3893
helpviewer_keywords:
- C3893
ms.assetid: 90d52eae-6ef2-4db1-b7ad-92f9e8b140fb
ms.openlocfilehash: 45a140d3fd5f510ee2434950ca3c4b47c0756d75
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385497"
---
# <a name="compiler-error-c3893"></a>Compilerfehler C3893

'Var': Verwendung l-Wertes eines Initonly-Datenmembers ist nur zulässig, in einem Instanzenkonstruktor der Klasse "Type_name"

Statische [Initonly](../../dotnet/initonly-cpp-cli.md) Datenmember können nur in einem statischen Konstruktor ihre Adresse haben.

Instanz (nicht statisch) Initonly-Datenmember können nur in den Instanzkonstruktoren (nicht statisch) ihre Adresse haben.

Im folgende Beispiel wird die C3893 generiert:

```
// C3893.cpp
// compile with: /clr
ref struct Y1 {
   Y1() : data_var(0) {
      int% i = data_var;   // OK
   }
   initonly int data_var;
};

int main(){
   Y1^ y= gcnew Y1;
   int% i = y->data_var;   // C3893
}
```