---
title: "Compilerwarnung (Stufe 1) C4952"
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
  - "C4952"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4952"
ms.assetid: 593324f0-5cfe-42fb-b221-2f71308765dd
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4952
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': Es wurden keine Profildaten in der Programmdatenbank 'pgd\_file' gefunden.  
  
 Bei der Verwendung von [\/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md) hat der Compiler ein Eingabemodul erkannt, das nach `/LTCG:PGINSTRUMENT` erneut kompiliert wurde und eine neue Funktion \(***Funktion***\) aufweist.  
  
 Diese Warnung dient nur zu Informationszwecken. Um diese Warnung zu beheben, führen Sie `/LTCG:PGINSTRUMENT` aus, wiederholen alle Testläufe und führen `/LTCG:PGOPTIMIZE` aus.  
  
 Bei Verwendung von `/LTCG:PGOPTIMIZE` würde diese Warnung durch einen Fehler ersetzt.