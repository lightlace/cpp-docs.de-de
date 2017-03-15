---
title: "Compilerwarnung (Stufe 4) C4960 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4960"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4960"
ms.assetid: 3b4ed286-9e8d-46f1-af0c-00ba669693a9
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 4) C4960
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"function" ist zu groß, um ein Profil zu erstellen  
  
 Bei Verwendung von [\/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) hat der Compiler ein Eingabemodul mit einer Funktion mit mehr als 65.535 Anweisungen erkannt. Eine so große Funktion ist für profilgesteuerte Optimierungen nicht verfügbar.  
  
 Verkleinern Sie die Funktion, um die Warnung aufzuheben.