---
title: "Compilerwarnung (Stufe 1) C4952 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4952"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4952"
ms.assetid: 593324f0-5cfe-42fb-b221-2f71308765dd
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 1) C4952
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': Es wurden keine Profildaten in der Programmdatenbank 'pgd\_file' gefunden.  
  
 Bei der Verwendung von [\/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md) hat der Compiler ein Eingabemodul erkannt, das nach `/LTCG:PGINSTRUMENT` erneut kompiliert wurde und eine neue Funktion \(***Funktion***\) aufweist.  
  
 Diese Warnung dient nur zu Informationszwecken. Um diese Warnung zu beheben, führen Sie `/LTCG:PGINSTRUMENT` aus, wiederholen alle Testläufe und führen `/LTCG:PGOPTIMIZE` aus.  
  
 Bei Verwendung von `/LTCG:PGOPTIMIZE` würde diese Warnung durch einen Fehler ersetzt.