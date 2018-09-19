---
title: Compilerfehler C3893 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3893
dev_langs:
- C++
helpviewer_keywords:
- C3893
ms.assetid: 90d52eae-6ef2-4db1-b7ad-92f9e8b140fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 857d13de61f03bf0784d8cd10ad092d16f7acdaa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087037"
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