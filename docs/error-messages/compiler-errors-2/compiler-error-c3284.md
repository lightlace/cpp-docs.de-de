---
title: Compilerfehler C3284
ms.date: 11/04/2016
f1_keywords:
- C3824
helpviewer_keywords:
- C3284
ms.assetid: e582f316-e9db-4d27-9c70-fdfa737a9d5f
ms.openlocfilehash: 6e79de18e277de9ee79945d319640fa906dea622
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511630"
---
# <a name="compiler-error-c3284"></a>Compilerfehler C3284

Die Einschränkungen für den generischen Parameter 'Parameter' der 'Funktion'-Funktion müssen mit den Einschränkungen für den generischen Parameter 'Parameter' der 'Funktion'-Funktion übereinstimmen.

Eine virtuelle generische Funktion muss die gleichen Einschränkungen wie eine virtuelle Funktion mit demselben Namen und Satz von Argumenten in der Basisklasse verwenden.

Im folgenden Beispiel wird C3284 generiert:

```
// C3284.cpp
// compile with: /clr /c
// C3284 expected
public interface class IGettable {
   int Get();
};

public interface class B {
   generic<typename T>
   where T : IGettable
   virtual int mf(T t);
};

public ref class D : public B {
public:
   generic<typename T>
   // Uncomment the following line to resolve.
   // where T : IGettable
   virtual int mf(T t) {
      return 4;
   }
};
```