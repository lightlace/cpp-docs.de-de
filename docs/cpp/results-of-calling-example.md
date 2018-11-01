---
title: Ergebnisse des Aufrufbeispiels
ms.date: 09/05/2018
helpviewer_keywords:
- examples [C++], results of calling
- results, thiscall call
- results, __fastcall keyword call
- results, __cdecl call
- results, __stdcall call
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
ms.openlocfilehash: 96582e48912bb591d869bbc4df179299e6459f1e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500936"
---
# <a name="results-of-calling-example"></a>Ergebnisse des Aufrufbeispiels

**Microsoft-spezifisch**

## <a name="cdecl"></a>__cdecl

Der ergänzte C-Funktionsname ist `_MyFunc`.

![CDECL-Aufrufkonvention](../cpp/media/vc37i01.gif "vc37I01") der **__cdecl** Aufrufkonvention

## <a name="stdcall-and-thiscall"></a>thiscall und __stdcall

Der ergänzte C-Name (**__stdcall**) ist `_MyFunc@20`. Der ergänzte C++-Name ist implementierungsspezifisch.

![&#95;&#95;StdCall und Thiscall-Aufrufkonventionen](../cpp/media/vc37i02.gif "vc37I02") __stdcall- und Thiscall-Aufrufkonventionen

## <a name="fastcall"></a>__fastcall

Der ergänzte C-Name (**__fastcall**) ist `@MyFunc@20`. Der ergänzte C++-Name ist implementierungsspezifisch.

![Aufrufkonvention für &#95; &#95;Fastcall](../cpp/media/vc37i03.gif "vc37I03") die "__fastcall"-Aufrufkonvention

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Aufrufbeispiel:Funktionsprototyp und Aufruf](../cpp/calling-example-function-prototype-and-call.md)