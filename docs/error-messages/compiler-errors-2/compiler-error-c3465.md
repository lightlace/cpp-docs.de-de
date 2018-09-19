---
title: Compilerfehler C3465 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3465
dev_langs:
- C++
helpviewer_keywords:
- C3465
ms.assetid: aeb815e5-b3fc-4525-afe2-d738e9321df1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6aa388d95904aecc8e1ba558b374249bb280e02
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048980"
---
# <a name="compiler-error-c3465"></a>Compilerfehler C3465

Um den Typ 'typ' zu verwenden, müssen Sie auf die Assembly 'assembly' verweisen.

Typweiterleitung funktioniert im Fall einer Clientanwendung bis zur erneuten Kompilierung des Clients. Bei der erneuten Kompilierung benötigen Sie einen Verweis auf jede Assembly, die die Definition eines in Ihrer Clientanwendung verwendeten Typs enthält.

Weitere Informationen finden Sie unter [Typweiterleitung (C++ / CLI)](../../windows/type-forwarding-cpp-cli.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel erstellt eine Assembly, die den neuen Speicherort eines Typs enthält.

```
// C3465.cpp
// compile with: /clr /LD
public ref class R {
public:
   ref class N {};
};
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine Assembly erstellt, die ursprünglich die Definition des Typs enthielt, jetzt jedoch Weiterleitungssyntax für den Typ enthält.

```
// C3465_b.cpp
// compile with: /clr /LD
#using "C3465.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3465 generiert:

```
// C3465_c.cpp
// compile with: /clr
// C3465 expected
#using "C3465_b.dll"
// Uncomment the following line to resolve.
// #using "C3465.dll"

int main() {
   R^ r = gcnew R();
}
```