---
title: Compilerwarnung (Stufe 1) C4488
ms.date: 11/04/2016
f1_keywords:
- C4488
helpviewer_keywords:
- C4488
ms.assetid: 55625e46-ddb5-4c7c-99c7-cd4aa9f879bd
ms.openlocfilehash: c3d176d034e679f3cca145ccb2fc77cc7fa64f3d
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73965575"
---
# <a name="compiler-warning-level-1-c4488"></a>Compilerwarnung (Stufe 1) C4488

"Function": erfordert das Schlüsselwort "Keyword" zum Implementieren der Schnittstellen Methode "Interface_method".

Eine Klasse muss alle Member einer Schnittstelle implementieren, von der Sie direkt erbt. Ein implementiertes Mitglied muss über öffentliche Zugriffsmöglichkeiten verfügen und als virtuell gekennzeichnet sein.

## <a name="example"></a>Beispiel

C4488 kann auftreten, wenn ein implementiertes Member nicht öffentlich ist. Im folgenden Beispiel wird C4488 generiert.

```cpp
// C4488.cpp
// compile with: /clr /c /W1 /WX
interface struct MyI {
   void f1();
};

// implemented member not public
ref class B : MyI { virtual void f1() {} };  // C4488

// OK
ref class C : MyI {
public:
   virtual void f1() {}
};
```

## <a name="example"></a>Beispiel

C4488 kann auftreten, wenn ein implementiertes Member nicht als virtuell markiert ist. Im folgenden Beispiel wird C4488 generiert.

```cpp
// C4488_b.cpp
// compile with: /clr /c /W1 /WX
interface struct MyI {
   void f1();
};

ref struct B : MyI { void f1() {} };   // C4488
ref struct C : MyI { virtual void f1() {} };   // OK
```