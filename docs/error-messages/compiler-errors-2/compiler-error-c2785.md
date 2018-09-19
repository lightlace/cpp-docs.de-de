---
title: Compilerfehler C2785 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2785
dev_langs:
- C++
helpviewer_keywords:
- C2785
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cfae8a58d9c42c9ddc3ef7779fc86f7157ba41b0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080856"
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