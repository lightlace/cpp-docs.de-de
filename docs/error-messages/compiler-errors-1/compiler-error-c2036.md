---
title: Compilerfehler C2036
ms.date: 11/04/2016
f1_keywords:
- C2036
helpviewer_keywords:
- C2036
ms.assetid: 895821a9-65d1-44b5-bde1-dae827f3e486
ms.openlocfilehash: c0d6c06a72e6ffbd2090577eeee9739394ee2791
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755095"
---
# <a name="compiler-error-c2036"></a>Compilerfehler C2036

' Identifier ': unbekannte Größe

Ein Vorgang auf `identifier` erfordert die Größe des Datenobjekts, das nicht ermittelt werden kann.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2036 generiert.

```
// C2036.c
// a C program
struct A* pA;
struct B { int i; } *pB;
int main() {
   pA++;   // C2036, size of A not known
   ((char*)pA)++;   // OK

   pB++;   // OK
}
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2036 generiert.

```cpp
// C2036_2.cpp
// a C++ program
struct A* pA;
int main() {
   pA++;   // C2036, size of A not known
   ((char*&)pA)++;   // OK, if sizeof(A) == sizeof(char)
}
```
