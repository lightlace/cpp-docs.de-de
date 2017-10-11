---
title: Ergebnisse des Aufrufbeispiels | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 5a1d6bf1c1d3cf2a57a74b7994766e940488a8e8
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="results-of-calling-example"></a>Ergebnisse des Aufrufbeispiels
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
  
## <a name="cdecl"></a>__cdecl  
 Der ergänzte C-Funktionsname ist "_MyFunc".  
  
 ![CDECL-Aufrufkonvention](../cpp/media/vc37i01.gif "vc37I01")  
Die __cdecl-Aufrufkonvention  
  
## <a name="stdcall-and-thiscall"></a>thiscall und __stdcall  
 Ergänzte C-Funktionsname (`__stdcall`) ist "_MyFunc@20." Der ergänzte C++-Name ist herstellereigen.  
  
 ![&#95; &#95; "stdcall" und Thiscall-Aufrufkonventionen](../cpp/media/vc37i02.gif "vc37I02")  
__stdcall- und thiscall-Aufrufkonventionen  
  
## <a name="fastcall"></a>__fastcall  
 Ergänzte C-Funktionsname (`__fastcall`) ist "@MyFunc@20." Der ergänzte C++-Name ist herstellereigen.  
  
 ![Die Aufrufkonvention für &#95; &#95; Fastcall](../cpp/media/vc37i03.gif "vc37I03")  
__fastcall-Aufrufkonvention  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufbeispiel:Funktionsprototyp und Aufruf](../cpp/calling-example-function-prototype-and-call.md)
