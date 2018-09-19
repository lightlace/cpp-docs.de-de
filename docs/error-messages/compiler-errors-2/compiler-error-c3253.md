---
title: Compilerfehler C3253 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3253
dev_langs:
- C++
helpviewer_keywords:
- C3253
ms.assetid: da40be26-0f78-4730-8727-ad11cddf8869
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f47ff3ab9094e7926453ec4eb5964485cf16f945
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065600"
---
# <a name="compiler-error-c3253"></a>Compilerfehler C3253

'Funktion': Fehler bei der expliziten Überschreibung

Eine explizite Überschreibung wurde falsch angegeben. Sie können nicht z. B. eine Implementierung für eine Außerkraftsetzung angeben, die Sie auch als reine angeben. Weitere Informationen finden Sie unter [explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md).

Im folgende Beispiel wird die C3253 generiert:

```
// C3253.cpp
// compile with: /clr
public interface struct I {
   void a();
   void b();
   void c();
};

public ref struct R : I {
   virtual void a() = 0, I::a {}   // C3253
   virtual void b() = I::a {}   // OK
   virtual void c() = 0;   // OK
};
```