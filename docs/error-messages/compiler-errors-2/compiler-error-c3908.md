---
title: Compilerfehler C3908 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3908
dev_langs:
- C++
helpviewer_keywords:
- C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7591b8ab5f8495b6af866e23e7a169b0f9cd29a6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047316"
---
# <a name="compiler-error-c3908"></a>Compilerfehler C3908

die Zugriffsebene ist weniger restriktiv als 'Konstrukt'

Eine Eigenschaftenaccessormethode ("Get" oder "Set") darf nicht weniger restriktiv als der Zugriff auf die Eigenschaft selbst zugreifen.  Auf ähnliche Weise für die Methoden der eigenschaftenzugriffsmethode.

Weitere Informationen finden Sie unter [Eigenschaft](../../windows/property-cpp-component-extensions.md) und [Ereignis](../../windows/event-cpp-component-extensions.md).

Im folgende Beispiel wird die C3908 generiert:

```
// C3908.cpp
// compile with: /clr
ref class X {
protected:
   property int i {
   public:   // C3908 property i is protected
      int get();
   private:
      void set(int);   // OK more restrictive
   };
};
```