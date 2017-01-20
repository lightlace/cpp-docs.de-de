---
title: "Compilerwarnung (Stufe 1) C4049"
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
  - "C4049"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4049"
ms.assetid: d11c1870-bcfc-4d71-8945-b87ec6ec3514
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4049
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compilerlimit: Ausgabe der Zeilennummer wird abgebrochen  
  
 Die Datei enthält mehr als 16.777.215 \(2<sup>24</sup>\-1\) Quellzeilen.  Der Compiler hört bei 16.777.215 mit der Nummerierung auf.  
  
 Für Code nach Zeile 16.777.215:  
  
-   Das Abbild enthält keine Debuginformationen für Zeilennummern.  
  
-   Einige Diagnosen werden möglicherweise mit falschen Zeilennummern angegeben.  
  
-   .asm\-Auflistungen \(\/FAs\) haben möglicherweise falsche Zeilennummern.