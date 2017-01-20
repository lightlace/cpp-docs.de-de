---
title: "Ergebnisse des Aufrufbeispiels"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Beispiele [C++], Ergebnisse des Aufrufs"
  - "Ergebnisse, __cdecl-Aufruf"
  - "Ergebnisse, __fastcall keyword (Aufruf)"
  - "Ergebnisse, __stdcall-Aufruf"
  - "Ergebnisse, thiscall-Aufruf"
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Ergebnisse des Aufrufbeispiels
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
  
## \_\_cdecl  
 Der ergänzte C\-Funktionsname ist "\_MyFunc".  
  
 ![CDECL&#45;Aufrufkonvention](../cpp/media/vc37i01.png "vc37I01")  
\_\_cdecl\-Aufrufkonvention  
  
## thiscall und \_\_stdcall  
 Der ergänzte C\-Funktionsname \(`__stdcall`\) ist "\_MyFunc@20". Der ergänzte C\+\+\-Name ist herstellereigen.  
  
 ![&#95;&#95;stdcall&#45; und thiscall&#45;Aufrufkonventionen](../cpp/media/vc37i02.png "vc37I02")  
\_\_stdcall\- und thiscall\-Aufrufkonventionen  
  
## \_\_fastcall  
 Der ergänzte C\-Funktionsname \(`__fastcall`\) ist "@MyFunc@20". Der ergänzte C\+\+\-Name ist herstellereigen.  
  
 ![Aufrufkonvention für &#95;&#95;fastcall](../cpp/media/vc37i03.png "vc37I03")  
\_\_fastcall\-Aufrufkonvention  
  
### END Microsoft\-spezifisch  
  
## Siehe auch  
 [Aufrufbeispiel: Funktionsprototyp und Aufruf](../cpp/calling-example-function-prototype-and-call.md)