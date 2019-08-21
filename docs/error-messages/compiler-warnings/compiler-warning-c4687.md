---
title: Compilerwarnung C4687
ms.date: 11/04/2016
f1_keywords:
- C4687
helpviewer_keywords:
- C4687
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
ms.openlocfilehash: 83f5c535f9cf252783110838c181c88c8b0096ee
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2019
ms.locfileid: "69631611"
---
# <a name="compiler-warning-c4687"></a>Compilerwarnung C4687

> "*Class*": eine versiegelte abstrakte Klasse kann keine Schnittstelle "*Schnitt*Stelle" implementieren.

## <a name="remarks"></a>Hinweise

Ein versiegelter, abstrakter Typ ist in der Regel nur nützlich, um statische Element Funktionen zu speichern.

Weitere Informationen finden Sie unter [abstract](../../extensions/abstract-cpp-component-extensions.md) und [sealed](../../extensions/sealed-cpp-component-extensions.md).

C4687 wird standardmäßig als Fehler ausgegeben. Sie können C4687 mit dem [Warning](../../preprocessor/warning.md) -Pragma unterdrücken. Wenn Sie sicher sind, dass Sie eine Schnittstelle in einem versiegelten, abstrakten Typ implementieren möchten, können Sie C4687 unterdrücken.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4687 generiert.

```cpp
// C4687.cpp
// compile with: /clr /c
interface class A {};

ref struct B sealed abstract : A {};   // C4687
ref struct C sealed : A {};   // OK
ref struct D abstract : A {};   // OK
```
