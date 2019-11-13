---
title: Compilerwarnung (Stufe 1) C4544
ms.date: 11/04/2016
f1_keywords:
- C4544
helpviewer_keywords:
- C4544
ms.assetid: 11ee04df-41ae-435f-af44-881e801315a8
ms.openlocfilehash: 094662270569c7362b7bb3c4953a466b19ed2e65
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966488"
---
# <a name="compiler-warning-level-1-c4544"></a>Compilerwarnung (Stufe 1) C4544

'declaration': Standardvorlagenargument wird für diese Vorlagendeklaration ignoriert

Ein Standardvorlagenargument wurde an einer falschen Position angegeben und wurde ignoriert. Ein Standardvorlagenargument für eine Klassenvorlage kann nur in der Deklaration oder Definition der Klassenvorlage und nicht auf einem Member der Klassenvorlage angegeben werden.

Im folgenden Beispiel wird C4545 generiert, und im nächsten Beispiel wird gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C4544.cpp
// compile with: /W1 /LD
template <class T>
struct S
{
   template <class T1>
      struct S1;
   void f();
};

template <class T=int>
template <class T1>
struct S<T>::S1 {};   // C4544
```

In diesem Beispiel gilt der Standardparameter für die Klassenvorlage `S`:

```cpp
// C4544b.cpp
// compile with: /LD
template <class T = int>
struct S
{
   template <class T1>
      struct S1;
   void f();
};

template <class T>
template <class T1>
struct S<T>::S1 {};
```