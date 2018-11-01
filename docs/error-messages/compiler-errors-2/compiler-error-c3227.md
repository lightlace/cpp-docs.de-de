---
title: Compilerfehler C3227
ms.date: 11/04/2016
f1_keywords:
- C3227
helpviewer_keywords:
- C3227
ms.assetid: 7939c23a-96c8-43c2-89e9-f217d132d155
ms.openlocfilehash: b175b14af55a9a462e040f064cc6e38d13fffb94
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632491"
---
# <a name="compiler-error-c3227"></a>Compilerfehler C3227

'Parameter': 'Schlüsselwort' kann nicht verwenden werden, um einen generischen Typ zuordnen

Um einen Typ zu instanziieren, ist ein geeigneter Konstruktor erforderlich. Allerdings kann der Compiler nicht sicherstellen, dass ein geeigneter Konstruktor verfügbar ist.

Sie können Vorlagen anstelle von Generika verwenden, um diesen Fehler zu beheben, oder Sie können eine von mehreren Methoden zum Erstellen einer Instanz des Typs.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3227 generiert.

```
// C3227.cpp
// compile with: /clr /c
generic<class T> interface class ICreate {
   static T Create();
};

generic <class T>
where T : ICreate<T>
ref class C {
   void f() {
      T t = new T;   // C3227

      // OK
      T t2 = ICreate<T>::Create();
      T t3 = safe_cast<T>( System::Activator::CreateInstance(T::typeid) );
   }
};
```