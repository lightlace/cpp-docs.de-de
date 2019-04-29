---
title: Compilerfehler C3807
ms.date: 11/04/2016
f1_keywords:
- C3807
helpviewer_keywords:
- C3807
ms.assetid: 7e2b0aab-8c61-4e71-b9c1-fcaeb6a1b5ea
ms.openlocfilehash: b5599914666af95a29667acc1ad4ad35eef7608f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391932"
---
# <a name="compiler-error-c3807"></a>Compilerfehler C3807

'Typ': eine Klasse mit dem ComImport-Attribut kann nicht von "Typ2" abgeleitet werden, nur eine schnittstellenimplementierung ist zulässig.

Ein Typ, der von abgeleitet <xref:System.Runtime.InteropServices.ComImportAttribute> können nur eine Schnittstelle implementieren.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3807 generiert.

```
// C3807.cpp
// compile with: /clr /c
ref struct S {};
interface struct I {};

[System::Runtime::InteropServices::ComImportAttribute()]
ref struct S1 : S {};   // C3807
ref struct S2 : I {};
```