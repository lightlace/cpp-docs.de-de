---
title: "Compilerwarnung (Stufe 4) C4710"
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
  - "C4710"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4710"
ms.assetid: 76381ec7-3fc1-4bee-9a0a-c2c8307b92e2
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4710
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Funktion ist nicht inline  
  
 Die festgelegte Funktion wurde als Inlinefunktion angegeben, aber nicht entsprechend erweitert.  
  
 Der Compiler entscheidet darüber, ob eine Inlinefunktion erweitert wird oder nicht.  Das **inline**\-Schlüsselwort dient wie das **register**\-Schlüsselwort als Hinweis für den Compiler.  Der Compiler ermittelt heuristisch, mit welchem Ziel eine bestimmte Inlinefunktion erweitert wird: Um den Code bei der Schnellkompilierung zu beschleunigen oder um den Codeumfang bei der platzsparenden Kompilierung zu verringern.  Bei der platzsparenden Kompilierung werden lediglich sehr kleine Funktionen vom Compiler in Inlinefunktionen erweitert.  
  
 In einigen Situationen erweitert der Compiler eine bestimmte Funktion aus technischen Gründen nicht "inline".  Unter [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) sind diese Gründe aufgeführt.  
  
 Diese Warnung ist standardmäßig deaktiviert.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md).