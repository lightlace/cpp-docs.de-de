---
title: Compilerwarnung (Stufe 1) C4489 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4489
dev_langs:
- C++
helpviewer_keywords:
- C4489
ms.assetid: 43b51c8c-27b5-44c9-b974-fe4b48f4896f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc019c618a5e4b8a453652573f6f407279792d56
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023253"
---
# <a name="compiler-warning-level-1-c4489"></a>Compilerwarnung (Stufe 1) C4489

"Spezifizierer": nicht zulässig für Schnittstellenmethode 'Methode'; Überschreiben Sie Bezeichner sind nur für Ref-Klasse und Werteklassenmethoden zulässig

Ein Bezeichner-Schlüsselwort wurde falsch auf Schnittstellenmethoden verwendet.

Weitere Informationen finden Sie unter [Überschreibungsspezifizierer](../../windows/override-specifiers-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4489 generiert.

```
// C4489.cpp
// compile with: /clr /c /W1
public interface class I {
   void f() new;   // C4489
   virtual void b() override;   // C4489

   void g();   // OK
};
```