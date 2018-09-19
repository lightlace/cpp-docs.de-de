---
title: Compilerfehler C3284 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3824
dev_langs:
- C++
helpviewer_keywords:
- C3284
ms.assetid: e582f316-e9db-4d27-9c70-fdfa737a9d5f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c6be84043d7c475cbd023d870e524f7bf9e6190
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46105213"
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