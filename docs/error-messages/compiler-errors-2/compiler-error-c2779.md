---
title: Compilerfehler C2779
ms.date: 11/04/2016
f1_keywords:
- C2779
helpviewer_keywords:
- C2779
ms.assetid: 4a00e492-855a-41f3-8a18-5f60ee20c2f2
ms.openlocfilehash: 7cf8aed276ab2aea61dc92b9e9fcbff9552c2ad6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449321"
---
# <a name="compiler-error-c2779"></a>Compilerfehler C2779

'Declaration': Eigenschaftenmethoden können nur mit nicht statischen Datenmember verbunden werden

Die `property` erweiterte-Attribut nicht ordnungsgemäß auf ein statisches Datenmember angewendet wird.

Im folgende Beispiel wird die C2779 generiert:

```
// C2779.cpp
struct A {
   static __declspec(property(put=PutProp))
   // try the following line instead
   __declspec(property(put=PutProp))
      int prop;   // C2779
   int PutProp(void);
};
```