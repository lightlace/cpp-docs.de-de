---
title: Compilerfehler C3893
ms.date: 11/04/2016
f1_keywords:
- C3893
helpviewer_keywords:
- C3893
ms.assetid: 90d52eae-6ef2-4db1-b7ad-92f9e8b140fb
ms.openlocfilehash: 20c17eaa6555b5511ecbc930eacdb2ec92475b23
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749502"
---
# <a name="compiler-error-c3893"></a>Compilerfehler C3893

"var": die Verwendung des l-Werts des initonly-Datenmembers ist nur in einem Instanzkonstruktor der Klasse "TYPE_NAME" zulässig.

Statische [initonly](../../dotnet/initonly-cpp-cli.md) -Datenmember können nur Ihre Adresse in einem statischen Konstruktor enthalten.

Instanzen (nicht statisch) initonly-Datenmember können nur Ihre Adresse in Instanzkonstruktoren (nicht statisch) enthalten.

Im folgenden Beispiel wird C3893 generiert:

```cpp
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
