---
title: Compilerwarnung (Ebenen 1 und 4) C4115 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4115
dev_langs:
- C++
helpviewer_keywords:
- C4115
ms.assetid: f3f94e72-fc49-4d09-b3e7-23d68e61152f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6c22e3c33f9ef2409c02f0e651473d566b4d2a74
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022525"
---
# <a name="compiler-warning-levels-1-and-4-c4115"></a>Compilerwarnung (Stufen 1 und 4) C4115

'Typ': Benannte Typdefinition in runden Klammern

Das angegebene Symbol wird verwendet, um eine Struktur, Union oder einen Aufzählungstyp innerhalb eines Klammerausdrucks zu definieren. Der Gültigkeitsbereich der Definition ist möglicherweise unerwartet.

Bei einem C-Funktionsaufruf weist die Definition einen globalen Gültigkeitsbereich auf. In einem C++-Aufruf weist die Definition denselben Gültigkeitsbereich wie die aufgerufene Funktion auf.

Diese Warnung kann auch durch Deklaratoren in Klammern (z. B. Prototypen) verursacht werden, die keine Ausdrücke in Klammern sind.

Dies ist eine Warnung der Stufe 1 für C++- und C#-Programme, die mit ANSI-Kompatibilität (/Za) kompiliert werden. Andernfalls handelt es sich um eine Warnung der Stufe 3.