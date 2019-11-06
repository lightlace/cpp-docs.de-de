---
title: Compilerwarnung C4368
ms.date: 11/04/2016
f1_keywords:
- C4368
helpviewer_keywords:
- C4368
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
ms.openlocfilehash: b1870d076d21c02574793a8079c4658b39ebf121
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73623647"
---
# <a name="compiler-warning-c4368"></a>Compilerwarnung C4368

'Member' kann nicht als Member des verwalteten 'Typs' definiert werden: Gemischte Typen werden nicht unterstützt

Sie können keinen systemeigenen Datenmember in einen CLR-Typ einbetten.

Sie können jedoch einen Zeiger auf einen systemeigenen Typ deklarieren und dessen Lebensdauer im Konstruktor, Destruktor und Finalizer der verwalteten Klasse steuern. Weitere Informationen finden Sie unter [debugtoren und Finalizer](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

Diese Warnmeldung wird immer als Fehler ausgegeben. Verwenden Sie das [Warning](../../preprocessor/warning.md) -Pragma, um C4368 zu deaktivieren.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4368 generiert.

```cpp
// C4368.cpp
// compile with: /clr /c
struct N {};
ref struct O {};
ref struct R {
    R() : m_p( new N ) {}
    ~R() { delete m_p; }

   property N prop;   // C4368
   int i[10];   // C4368

   property O ^ prop2;   // OK
   N * m_p;   // OK
};
```