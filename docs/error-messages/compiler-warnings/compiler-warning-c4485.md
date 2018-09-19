---
title: Compilerwarnung C4485 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4485
dev_langs:
- C++
helpviewer_keywords:
- C4485
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb83700bf8ca79960599d85ed3d335f80c9fc7f2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117750"
---
# <a name="compiler-warning-c4485"></a>Compilerwarnung C4485

'Überschreibungsfunktion': entspricht der Klassenmethode "Basisklassenfunktion" Basismethode der Verweisklasse ist allerdings nicht markierte 'new' oder 'override'; "new" (und "virtual") werden angenommen.

Überschreibt ein Accessor, mit oder ohne die `virtual` -Schlüsselwort, eine Basisklasse Accessor-Funktion, aber die `override` oder `new` Spezifizierer war nicht Teil der überschreibenden Funktionssignatur. Hinzufügen der `new` oder `override` Spezifizierer, um diese Warnung zu beheben.

Finden Sie unter [überschreiben](../../windows/override-cpp-component-extensions.md) und [new (neuer Slot in Vtable)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md) für Weitere Informationen.

C4485 wird immer als Fehler ausgegeben. Verwenden der [Warnung](../../preprocessor/warning.md) Pragma C4485 zu unterdrücken.

## <a name="example"></a>Beispiel

Das folgende Beispiel generiert C4485

```
// C4485.cpp
// compile with: /clr
delegate void Del();

ref struct A {
   virtual event Del ^E;
};

ref struct B : A {
   virtual event Del ^E;   // C4485
};

ref struct C : B {
   virtual event Del ^E {
      void raise() override {}
      void add(Del ^) override {}
      void remove(Del^) override {}
   }
};
```