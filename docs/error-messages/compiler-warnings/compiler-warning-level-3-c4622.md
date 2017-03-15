---
title: "Compilerwarnung (Stufe 3) C4622 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4622"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4622"
ms.assetid: d3c879f0-4492-4f4b-b26d-230993f3a933
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 3) C4622
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Überschreiben der Debuginformationen, die beim Erstellen des vorkompilierten Headers in der Objektdatei angelegt wurden: „file“  
  
 Die Codeansichtsinformationen in der angegebenen Datei sind bei der Kompilierung mit der [\/Yu](../../build/reference/yu-use-precompiled-header-file.md)\-Option \(Vorkompilierte Header verwenden\) verloren gegangen.  
  
 Benennen Sie die Objektdatei \(mit [\/Fo](../../build/reference/fo-object-file-name.md)\) beim Erstellen oder Verwenden der vorkompilierten Headerdatei um, und stellen Sie eine Verknüpfung mit der neuen Objektdatei her.