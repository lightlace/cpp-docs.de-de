---
title: Compilerfehler C3209
ms.date: 11/04/2016
f1_keywords:
- C3209
helpviewer_keywords:
- C3209
ms.assetid: 1de44e39-69d1-4894-8f89-ff92136e8e5d
ms.openlocfilehash: f907d0605cccf0a36abd1361d8c87a783bb81506
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243244"
---
# <a name="compiler-error-c3209"></a>Compilerfehler C3209

'Klasse': generische Klasse muss eine verwaltete oder WinRTclass sein.

Eine generische Klasse muss eine verwaltete Klasse oder eine Windows-Runtime-Klasse sein.

Im folgenden Beispiel wird C3209 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C3209.cpp
// compile with: /clr
generic <class T>
class C {};   // C3209

// OK - ref class can be generic
generic <class T>
ref class D {};
```