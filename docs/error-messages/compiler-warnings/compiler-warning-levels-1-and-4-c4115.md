---
title: "Compilerwarnung (Stufen 1 und 4) C4115"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C4115"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4115"
ms.assetid: f3f94e72-fc49-4d09-b3e7-23d68e61152f
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufen 1 und 4) C4115
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ': Benannte Typdefinition in runden Klammern  
  
 Das angegebene Symbol wird verwendet, um eine Struktur, Union oder einen Aufzählungstyp innerhalb eines Klammerausdrucks zu definieren. Der Gültigkeitsbereich der Definition ist möglicherweise unerwartet.  
  
 Bei einem C\-Funktionsaufruf weist die Definition einen globalen Gültigkeitsbereich auf. In einem C\+\+\-Aufruf weist die Definition denselben Gültigkeitsbereich wie die aufgerufene Funktion auf.  
  
 Diese Warnung kann auch durch Deklaratoren in Klammern \(z. B. Prototypen\) verursacht werden, die keine Ausdrücke in Klammern sind.  
  
 Dies ist eine Warnung der Stufe 1 für C\+\+\- und C\#\-Programme, die mit ANSI\-Kompatibilität \(\/Za\) kompiliert werden. Andernfalls handelt es sich um eine Warnung der Stufe 3.