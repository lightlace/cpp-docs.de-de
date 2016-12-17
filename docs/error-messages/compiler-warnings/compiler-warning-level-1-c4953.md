---
title: "Compilerwarnung (Stufe 1) C4953"
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
  - "C4953"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4953"
ms.assetid: 3c4f6ac6-3976-41ab-8a27-3c41d7472ea7
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4953
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Inlinee "function" wurde bearbeitet, seit die Konfigurationsdaten erfasst wurden. Die Profildaten werden nicht verwendet  
  
 Bei Verwendung von [\/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md) hat der Compiler ein Eingabemodul erkannt, das nach `/LTCG:PGINSTRUMENT` neu kompiliert wurde und eine Funktion \(***function***\) aufweist, die bearbeitet wurde und die in vorhandenen Testläufen als Kandidat für Inlining identifiziert wurde. Infolge der Neukompilierung des Moduls ist die Funktion jedoch kein Kandidat für Inlining mehr.  
  
 Diese Warnung dient nur zu Informationszwecken. Um diese Warnung zu beheben, führen Sie `/LTCG:PGINSTRUMENT` aus, wiederholen alle Testläufe und führen `/LTCG:PGOPTIMIZE` aus.  
  
 Bei Verwendung von `/LTCG:PGOPTIMIZE` würde diese Warnung durch einen Fehler ersetzt.