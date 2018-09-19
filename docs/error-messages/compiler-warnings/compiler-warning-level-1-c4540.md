---
title: Compilerwarnung (Stufe 1) C4540 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4540
dev_langs:
- C++
helpviewer_keywords:
- C4540
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e3f553bd1f910c7b17e079dc1f03664c78383e3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042766"
---
# <a name="compiler-warning-level-1-c4540"></a>Compilerwarnung (Stufe 1) C4540

Dynamic_cast zum Konvertieren in nichtverfügbare oder mehrdeutige Basisklasse verwendet; Laufzeit-Test schlägt fehl, ('Typ1' zu 'Typ2')

Sie verwendet haben `dynamic_cast` , die von einem Typ in einen anderen konvertieren. Der Compiler ermittelt, dass immer die Umwandlung fehlschlägt (zurückgeben **NULL**), da eine Basisklasse zugegriffen werden kann (`private`, z. B.) oder nicht eindeutig (mehr als einmal in der Klassenhierarchie, z. B.).

Das folgende Beispiel zeigt ein Beispiel für diese Warnung aus. Klasse **B** ergibt sich aus der Klasse **ein**. Das Programm verwendet `dynamic_cast` zum Umwandeln von Klasse **B** (die abgeleitete Klasse) Klasse **ein**, die schlägt immer fehl, da Klasse **B** ist `private` und somit kann nicht zugegriffen werden. Ändern den Zugriff auf **ein** zu **öffentliche** die Warnung aufgelöst wird.

```
// C4540.cpp
// compile with: /W1

struct A {
   virtual void g() {}
};

struct B : private A {
   virtual void g() {}
};

int main() {
   B b;
   A * ap = dynamic_cast<A*>(&b);   // C4540
}
```