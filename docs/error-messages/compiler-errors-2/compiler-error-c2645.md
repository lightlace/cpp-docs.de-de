---
title: Compilerfehler C2645
ms.date: 11/04/2016
f1_keywords:
- C2645
helpviewer_keywords:
- C2645
ms.assetid: 6609c2fa-c3b2-4a6b-8e8d-58fb52f67175
ms.openlocfilehash: 9df9f41da3d4cbef97511b979845c5a6b404614b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152591"
---
# <a name="compiler-error-c2645"></a>Compilerfehler C2645

kein vollständiger Name für Elementzeiger (gefunden ":: *")

Die Deklaration eines Zeigers auf einen Member gibt keine Klasse an.

Im folgende Beispiel wird die C2645 generiert:

```
// C2645.cpp
class A {};
int main() {
   int B::* bp;   // C2645 B not defined
   int A::* ap;   // OK
}
```