---
title: "Compilerwarnung (Stufe 4) C4233 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4233"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4233"
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 4) C4233
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht dem Standard entsprechende Erweiterung: Schlüsselwort 'Schlüsselwort' wird nur in C\+\+ unterstützt und nicht in C  
  
 Der Compiler hat den Quellcode in C anstatt in C\+\+ kompiliert, Sie haben jedoch ein Schlüsselwort verwendet, das nur in C\+\+ gültig ist.  Der Compiler kompiliert die Quelldatei in C, wenn die Erweiterung der Quelldatei **.c** lautet oder [\/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)\) verwendet wird.  
  
 Diese Warnung wird automatisch zu einem Fehler heraufgestuft.  Um dieses Verhalten zu ändern, verwenden Sie [\#pragma warning](../../preprocessor/warning.md).  Um C4233 beispielsweise in eine Warnung der Stufe 4 umzuwandeln, verwenden Sie  
  
```  
#pragma warning(2:4233)  
```  
  
 in der Quellcodedatei.