---
title: Linkertoolfehler LNK2033
ms.date: 11/04/2016
f1_keywords:
- LNK2033
helpviewer_keywords:
- LNK2033
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
ms.openlocfilehash: 7e95823e23215848ff3e5d201171523c9009eb2d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62298905"
---
# <a name="linker-tools-error-lnk2033"></a>Linkertoolfehler LNK2033

nicht aufgelöstes Typeref-Token (Token) für 'Typ'

Ein Typ keine Definition in den MSIL-Metadaten.

LNK2033 kann auftreten, bei der Kompilierung mit **/CLR: safe** und es ist nur eine Vorwärtsdeklaration für einen Typ in einer MSIL-Modul, in denen der Typ in den MSIL-Modul verwiesen wird.

Der Typ muss definiert werden, unter **/CLR: safe**.

Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die LNK2033 generiert.

```
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