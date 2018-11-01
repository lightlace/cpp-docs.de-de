---
title: Linkertoolwarnung LNK4248
ms.date: 11/04/2016
f1_keywords:
- LNK4248
helpviewer_keywords:
- LNK4248
ms.assetid: e40523ff-e3cb-4ba6-ab79-23f0f339f6cf
ms.openlocfilehash: db9432c505b7348c9bef5ed34aac1cb4edecb17b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50461229"
---
# <a name="linker-tools-warning-lnk4248"></a>Linkertoolwarnung LNK4248

nicht aufgelöstes Typeref-Token (Token) für 'Typ'. Image kann möglicherweise nicht ausgeführt.

Ein Typ keine Definition in den MSIL-Metadaten.

LNK4248 kann auftreten, wenn es nur eine Vorwärtsdeklaration für einen Typ in einer MSIL-Modul ist (kompiliert mit **"/ CLR"**), auf den Typ im MSIL-Modul verwiesen wird, und die MSIL-Modul mit einem systemeigenen Modul verknüpft ist, die eine Definition für Der Typ.

In diesem Fall der Linker bietet die native Typdefinition in den MSIL-Metadaten, und dies kann für das korrekte Verhalten bereitstellen.

Allerdings ist eine Vorwärts-Typdeklaration einen CLR-Typ, systemeigene Typdefinition des Linkers nicht richtig möglicherweise

Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Geben Sie die Typdefinition in das MSIL-Modul.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die LNK4248 generiert. Definieren Sie die Struktur ein aufgelöst.

```
// LNK4248.cpp
// compile with: /clr /W1
// LNK4248 expected
struct A;
void Test(A*){}

int main() {
   Test(0);
}
```

## <a name="example"></a>Beispiel

Im folgende Beispiel verfügt über eine forward-Definition eines Typs.

```
// LNK4248_2.cpp
// compile with: /clr /c
class A;   // provide a definition for A here to resolve
A * newA();
int valueA(A * a);

int main() {
   A * a = newA();
   return valueA(a);
}
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die LNK4248 generiert.

```
// LNK4248_3.cpp
// compile with: /c
// post-build command: link LNK4248_2.obj LNK4248_3.obj
class A {
public:
   int b;
};

A* newA() {
   return new A;
}

int valueA(A * a) {
   return (int)a;
}
```