---
title: Compilerwarnung (Stufen 1 und 4) C4115
ms.date: 11/04/2016
f1_keywords:
- C4115
helpviewer_keywords:
- C4115
ms.assetid: f3f94e72-fc49-4d09-b3e7-23d68e61152f
ms.openlocfilehash: 20e44eba3b6f6079e6f37b7cf33fa530a996e829
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462958"
---
# <a name="compiler-warning-levels-1-and-4-c4115"></a>Compilerwarnung (Stufen 1 und 4) C4115

'Typ': Benannte Typdefinition in runden Klammern

Das angegebene Symbol wird verwendet, um eine Struktur, Union oder einen Aufzählungstyp innerhalb eines Klammerausdrucks zu definieren. Der Gültigkeitsbereich der Definition ist möglicherweise unerwartet.

Bei einem C-Funktionsaufruf weist die Definition einen globalen Gültigkeitsbereich auf. In einem C++-Aufruf weist die Definition denselben Gültigkeitsbereich wie die aufgerufene Funktion auf.

Diese Warnung kann auch durch Deklaratoren in Klammern (z. B. Prototypen) verursacht werden, die keine Ausdrücke in Klammern sind.

Dies ist eine Warnung der Stufe 1 für C++- und C#-Programme, die mit ANSI-Kompatibilität (/Za) kompiliert werden. Andernfalls handelt es sich um eine Warnung der Stufe 3.