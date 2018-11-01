---
title: Compilerfehler C2785
ms.date: 11/04/2016
f1_keywords:
- C2785
helpviewer_keywords:
- C2785
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
ms.openlocfilehash: fcf2bbb01f2aac668ff52884a6ccfb36c66aa89d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445838"
---
# <a name="compiler-error-c2785"></a>Compilerfehler C2785

'Deklaration1' und 'Deklaration2' haben verschiedene Rückgabetypen

Der Rückgabetyp der funktionsvorlagenspezialisierung unterscheidet sich von der Rückgabetyp der Hauptfunktion Vorlage.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Überprüfen Sie alle spezialisierungen der Funktionsvorlage für Konsistenz.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2785 generiert:

```
// C2785.cpp
// compile with: /c
template<class T> void f(T);

template<> int f(int); // C2785
template<> void f(int); // OK
```