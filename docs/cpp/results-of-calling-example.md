---
title: Ergebnisse des Aufrufbeispiels
ms.date: 11/19/2018
helpviewer_keywords:
- examples [C++], results of calling
- results, thiscall call
- results, __fastcall keyword call
- results, __cdecl call
- results, __stdcall call
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
ms.openlocfilehash: dcd1f9002362b7726883c6ce4f74fda9ab593544
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175410"
---
# <a name="results-of-calling-example"></a>Ergebnisse des Aufrufbeispiels

**Microsoft-spezifisch**

## <a name="cdecl"></a>__cdecl

Der ergänzte C-Funktionsname ist `_MyFunc`.

![CDECL-Aufrufkonvention](../cpp/media/vc37i01.gif "CDECL-Aufrufkonvention") <br/>
Die **__cdecl** Aufrufkonvention

## <a name="stdcall-and-thiscall"></a>thiscall und __stdcall

Der ergänzte C-Name (**__stdcall**) ist `_MyFunc@20`. Der ergänzte C++-Name ist implementierungsspezifisch.

![&#95;&#95;StdCall und Thiscall-Aufrufkonventionen](../cpp/media/vc37i02.gif "&#95;&#95;Stdcall und Thiscall-Aufrufkonventionen") <br/>
__stdcall- und thiscall-Aufrufkonventionen

## <a name="fastcall"></a>__fastcall

Der ergänzte C-Name (**__fastcall**) ist `@MyFunc@20`. Der ergänzte C++-Name ist implementierungsspezifisch.

![Aufrufkonvention für &#95; &#95;Fastcall](../cpp/media/vc37i03.gif "Aufrufkonvention für &#95; &#95;Fastcall") <br/>
__fastcall-Aufrufkonvention

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Aufrufbeispiel:Funktionsprototyp und Aufruf](../cpp/calling-example-function-prototype-and-call.md)