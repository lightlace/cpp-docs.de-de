---
title: Ergebnisse des Aufrufbeispiels | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- examples [C++], results of calling
- results, thiscall call
- results, __fastcall keyword call
- results, __cdecl call
- results, __stdcall call
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eaa47af17e46f51ef92cc15b8d2275b2ed8e05f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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