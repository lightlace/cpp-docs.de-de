---
title: Linkertoolwarnung LNK4248
ms.date: 11/04/2016
f1_keywords:
- LNK4248
helpviewer_keywords:
- LNK4248
ms.assetid: e40523ff-e3cb-4ba6-ab79-23f0f339f6cf
ms.openlocfilehash: 4ba05ef067c539dc9c0aca6dc2a395748fd217a2
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988103"
---
# <a name="linker-tools-warning-lnk4248"></a>Linkertoolwarnung LNK4248

nicht aufgelöstes TypeRef-Token (Token) für ' Typ '; Image kann möglicherweise nicht ausgeführt werden

Ein Typ verfügt nicht über eine Definition in den MSIL-Metadaten.

Linkertoolwarnung LNK4248 kann auftreten, wenn in einem MSIL-Modul (mit **/CLR**kompiliert) nur eine vorwärts Deklaration für einen Typ vorhanden ist, bei der im MSIL-Modul auf den Typ verwiesen wird und das MSIL-Modul mit einem systemeigenen Modul verknüpft ist, das über eine Definition für den Typ verfügt.

In dieser Situation stellt der Linker die Definition des systemeigenen Typs in den MSIL-Metadaten bereit, und dies kann das korrekte Verhalten bereitstellen.

Wenn eine vorwärts-Typdeklaration jedoch ein CLR-Typ ist, ist die native Typdefinition des Linkers möglicherweise nicht korrekt.

Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Geben Sie die Typdefinition im MSIL-Modul an.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird Linkertoolwarnung LNK4248 generiert. Definieren Sie die zu lösende Struktur A.

```cpp
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

Das folgende Beispiel weist eine vorwärts Definition eines Typs auf.

```cpp
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

Im folgenden Beispiel wird Linkertoolwarnung LNK4248 generiert.

```cpp
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
