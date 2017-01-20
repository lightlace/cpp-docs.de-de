---
title: "Linkertoolfehler LNK1264"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1264"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1264"
ms.assetid: 23b1aad7-d382-42c1-bae8-db68575c57a8
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK1264
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/LTCG:PGINSTRUMENT wurde angegeben, aber Codegenerierung ist nicht erforderlich. Die Instrumentation ist fehlgeschlagen  
  
 **\/LTCG:PGINSTRUMENT** wurde angegeben, es wurden jedoch keine OBJ\-Dateien gefunden, die mit [\/GL](../../build/reference/gl-whole-program-optimization.md) kompiliert wurden.  Die Instrumentation kann nicht stattfinden, und der Link schlug fehl.  Die Instrumentation ist nur möglich, wenn in der Befehlszeile mindestens eine OBJ\-Datei angegeben wird, die mit **\/GL** kompiliert wurde.  
  
 PGO \(Profile Guided Optimization\) ist nur in 64\-Bit\-Compilern verfügbar.