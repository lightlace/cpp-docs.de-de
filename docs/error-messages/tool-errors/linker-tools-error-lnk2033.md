---
title: Linkertoolfehler Lnk2033 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2033
dev_langs:
- C++
helpviewer_keywords:
- LNK2033
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6c547b4d35e2e7fe057cdd67f0dad47f58d000c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039990"
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