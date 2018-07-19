---
title: Ergebnisse des Aufrufbeispiels | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- examples [C++], results of calling
- results, thiscall call
- results, __fastcall keyword call
- results, __cdecl call
- results, __stdcall call
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0e7b022925e22f021a2ddad1b3b9ef52924b25a3
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939106"
---
# <a name="results-of-calling-example"></a>Ergebnisse des Aufrufbeispiels
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
  
## <a name="cdecl"></a>__cdecl  
 Der ergänzte C-Funktionsname ist "_MyFunc".  
  
 ![CDECL-Aufrufkonvention](../cpp/media/vc37i01.gif "vc37I01")  
Die __cdecl-Aufrufkonvention  
  
## <a name="stdcall-and-thiscall"></a>thiscall und __stdcall  
 Der ergänzte C-Name (**__stdcall**) ist "_MyFunc@20." Der ergänzte C++-Name ist herstellereigen.  
  
 ![&#95;&#95;StdCall und Thiscall-Aufrufkonventionen](../cpp/media/vc37i02.gif "vc37I02")  
__stdcall- und thiscall-Aufrufkonventionen  
  
## <a name="fastcall"></a>__fastcall  
 Der ergänzte C-Name (**__fastcall**) ist "@MyFunc@20." Der ergänzte C++-Name ist herstellereigen.  
  
 ![Aufrufkonvention für &#95; &#95;Fastcall](../cpp/media/vc37i03.gif "vc37I03")  
__fastcall-Aufrufkonvention  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufbeispiel:Funktionsprototyp und Aufruf](../cpp/calling-example-function-prototype-and-call.md)