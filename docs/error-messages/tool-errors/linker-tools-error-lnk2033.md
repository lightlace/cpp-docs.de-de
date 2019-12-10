---
title: Linkertoolfehler LNK2033
ms.date: 11/04/2016
f1_keywords:
- LNK2033
helpviewer_keywords:
- LNK2033
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
ms.openlocfilehash: 407f5eaf94a0e2da43425c3bbdd1955a88c95f14
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991176"
---
# <a name="linker-tools-error-lnk2033"></a>Linkertoolfehler LNK2033

nicht aufgelöstes TypeRef-Token (Token) für "Type".

Ein Typ verfügt nicht über eine Definition in den MSIL-Metadaten.

Linkertoolfehler LNK2033 kann auftreten, wenn mit **/clr: Safe** kompiliert wird und nur eine vorwärts Deklaration für einen Typ in einem MSIL-Modul vorhanden ist, bei dem im MSIL-Modul auf den Typ verwiesen wird.

Der Typ muss unter **/clr: Safe**definiert werden.

Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird Linkertoolfehler LNK2033 generiert.

```cpp
// LNK2033.cpp
// compile with: /clr:safe
// LNK2033 expected
ref class A;
ref class B {};

int main() {
   A ^ aa = nullptr;
   B ^ bb = nullptr;   // OK
};
```
