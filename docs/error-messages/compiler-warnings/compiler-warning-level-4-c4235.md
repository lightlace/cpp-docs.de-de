---
title: "Compilerwarnung (Stufe 4) C4235 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4235"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4235"
ms.assetid: d4214799-d62c-4674-b4e2-9e201c303303
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 4) C4235
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht dem Standard entsprechende Erweiterung: Das Schlüsselwort 'Schlüsselwort' wird für diese Architektur nicht unterstützt  
  
 Das von Ihnen verwendete Schlüsselwort wird vom Compiler nicht unterstützt.  
  
 Diese Warnung wird automatisch zu einem Fehler heraufgestuft.  Um dieses Verhalten zu ändern, verwenden Sie [\#pragma warning](../../preprocessor/warning.md).  Um C4235 beispielsweise in eine Warnung der Stufe 2 umzuwandeln, verwenden Sie folgende Codezeile  
  
```  
#pragma warning(2:4235)  
```  
  
 in der Quellcodedatei.