---
title: Compilerwarnung (Stufe 1) C4540
ms.date: 11/04/2016
f1_keywords:
- C4540
helpviewer_keywords:
- C4540
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
ms.openlocfilehash: 86f6cd866f7708277ebba436ba7c076086dc9c8c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473670"
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