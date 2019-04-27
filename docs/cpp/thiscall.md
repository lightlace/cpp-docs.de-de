---
title: __thiscall
ms.date: 11/04/2016
f1_keywords:
- __thiscall
- __thiscall_cpp
helpviewer_keywords:
- __thiscall keyword [C++]
ms.assetid: a6a22dd2-0101-4885-b33b-22f6057965df
ms.openlocfilehash: fc5a32fedf52377889b61103856e2125733cd696
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266781"
---
# <a name="thiscall"></a>__thiscall

**Microsoft-spezifisch**

Die **__thiscall** Aufrufkonvention wird für Memberfunktionen verwendet und ist der Standardwert ein, die Aufrufkonvention C++ Memberfunktionen, die keine Variablen Argumente verwenden. Klicken Sie unter **__thiscall**, der aufgerufene entleert den Stapel, handelt es sich nicht `vararg` Funktionen. Argumente werden von rechts nach links, auf dem Stapel abgelegt, mit der **dies** Zeiger übergeben wird, über das Register "ECX" und nicht auf dem Stapel, auf die X86 Architektur.

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