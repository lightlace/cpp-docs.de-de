---
title: Compilerfehler C3445
ms.date: 04/10/2017
f1_keywords:
- C3445
helpviewer_keywords:
- C3445
ms.assetid: 0d272bfc-136b-4025-a9ba-5e4eea5f8215
ms.openlocfilehash: 2eddeb5a56c953ca0864e29187fbe28c53bdee24
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328645"
---
# <a name="compiler-error-c3445"></a>Compilerfehler C3445

> Copy-List-Initialisierung von "*Typ*' können keine expliziten Konstruktor

Gemäß dem ISO C ++ 17-standard der Compiler ist erforderlich, um einen expliziten Konstruktor für die Auflösung von funktionsüberladungen im Copy-List-Initialisierung zu berücksichtigen, aber muss ein Fehler ausgelöst, wenn diese Überladung tatsächlich ausgewählt wird.

Ab Visual Studio 2017, sucht der Compiler Fehler im Zusammenhang mit der Erstellung von Objekten mithilfe einer Initialisiererliste, die von Visual Studio 2015 nicht gefunden wurden. Dieser Fehler können zu Abstürzen oder nicht definiertem Verhalten zur Laufzeit führen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C3445 generiert.

```cpp
// C3445.cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    A a1 = { 1 };     // error C3445: copy-list-initialization of
                      //     'A' cannot use an explicit constructor
}
```

Verwenden Sie stattdessen direkte Initialisierung, um den Fehler zu beheben:

```cpp
// C3445b.cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    A a1{ 1 };
}
```
