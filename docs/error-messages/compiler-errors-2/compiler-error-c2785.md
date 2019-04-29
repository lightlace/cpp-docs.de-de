---
title: Compilerfehler C2785
ms.date: 11/04/2016
f1_keywords:
- C2785
helpviewer_keywords:
- C2785
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
ms.openlocfilehash: fcf2bbb01f2aac668ff52884a6ccfb36c66aa89d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395377"
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