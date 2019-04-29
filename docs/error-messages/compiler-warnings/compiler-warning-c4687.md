---
title: Compilerwarnung C4687
ms.date: 11/04/2016
f1_keywords:
- C4687
helpviewer_keywords:
- C4687
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
ms.openlocfilehash: 1978e1a35ba5b5d59b5961a21378d8af6921d145
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311317"
---
# <a name="compiler-warning-c4687"></a>Compilerwarnung C4687

'Klasse': eine versiegelte abstrakte Klasse kann eine Schnittstelle "Schnittstelle" nicht implementieren

Ein Typ versiegelter, "abstract" eignet sich in der Regel nur auf statische Memberfunktionen enthalten.

Weitere Informationen finden Sie unter [abstrakte](../../extensions/abstract-cpp-component-extensions.md)und [versiegelten](../../extensions/sealed-cpp-component-extensions.md).

C4687 wird standardmäßig als Fehler ausgegeben. Sie können C4687 mit Unterdrücken der [Warnung](../../preprocessor/warning.md) Pragma. Wenn Sie sicher sind, dass Sie in einem versiegelten "," abstract-Typ eine Schnittstelle implementieren möchten, können Sie C4687 unterdrücken.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4687 generiert.

```
// C4687.cpp
// compile with: /clr /c
interface class A {};

ref struct B sealed abstract : A {};   // C4687
ref struct C sealed : A {};   // OK
ref struct D abstract : A {};   // OK
```