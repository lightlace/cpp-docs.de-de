---
title: __thiscall | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __thiscall
- __thiscall_cpp
dev_langs:
- C++
helpviewer_keywords:
- __thiscall keyword [C++]
ms.assetid: a6a22dd2-0101-4885-b33b-22f6057965df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: af20b6d406b0e2119df04d5348c554b3405e8597
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103372"
---
# <a name="thiscall"></a>__thiscall

**Microsoft-spezifisch**

Die **__thiscall** -Aufrufkonvention wird für Memberfunktionen verwendet und ist die Standardaufrufkonvention, die von C++-Memberfunktionen, die keine Variablen Argumente verwenden, verwendet. Klicken Sie unter **__thiscall**, der aufgerufene entleert den Stapel, handelt es sich nicht `vararg` Funktionen. Argumente werden von rechts nach links, auf dem Stapel abgelegt, mit der **dies** Zeiger übergeben wird, über das Register "ECX" und nicht auf dem Stapel, auf die X86 Architektur.

Ein Grund für die Verwendung **__thiscall** ist in Klassen, deren Memberfunktionen `__clrcall` standardmäßig. In diesem Fall können Sie **__thiscall** auf einzelne Member von systemeigenem Code funktioniert.

Beim Kompilieren mit [/CLR: pure](../build/reference/clr-common-language-runtime-compilation.md), alle Funktionen und Funktionszeiger `__clrcall` sofern nicht anders angegeben. Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

In Versionen vor Visual C++ 2005 die **__thiscall** Aufrufkonvention nicht explizit angegeben werden in einem Programm, da **__thiscall** kein Schlüsselwort war.

`vararg` Memberfunktionen der **__cdecl** Aufrufkonvention. Alle Funktionsargumente werden auf dem Stapel abgelegt, mit der **dies** Zeiger zuletzt auf dem Stapel abgelegt

Da diese Aufrufkonvention nur für C++ gültig ist, gibt es kein Schema zur C-Namensergänzung.

Auf ARM und X64 Computern **__thiscall** akzeptiert und vom Compiler ignoriert.

Wenn die Funktion bei nicht statischen Klassenfunktionen abweichend definiert ist, muss der Aufrufkonventionsmodifizierer nicht in der abweichenden Definition angegeben werden. Das bedeutet, dass für nicht statische Membermethoden der Klasse zum Zeitpunkt der Definition die während der Deklaration angegebene Aufrufkonvention angenommen wird.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Argumentübergabe und Benennungskonventionen](../cpp/argument-passing-and-naming-conventions.md)