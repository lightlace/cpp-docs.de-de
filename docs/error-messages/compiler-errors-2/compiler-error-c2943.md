---
title: Compilerfehler C2943
ms.date: 11/04/2016
f1_keywords:
- C2943
helpviewer_keywords:
- C2943
ms.assetid: ede6565e-d892-44c0-8eee-c69545f3be2e
ms.openlocfilehash: 53340611ef92aac7c9bed30f364fed424fdfe140
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366276"
---
# <a name="compiler-error-c2943"></a>Compilerfehler C2943

'Klasse': 'Typ-Klasse-ID' wird als Typargument einer Vorlage neu definiert.

Eine generische oder Vorlagenklasse kann nicht anstelle eines Symbols als generisches oder Vorlagentypargument verwendet werden.

Im folgenden Beispiel wird C2943 generiert.

```
// C2943.cpp
// compile with: /c
template<class T>
class List {};

template<class List<int> > class MyList;   // C2943
template<class T >  class MyList;
```