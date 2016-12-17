---
title: "Reihenfolge von CL-Optionen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "cl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe-Compiler, Festlegen von Optionen"
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Reihenfolge von CL-Optionen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Optionen können an beliebiger Stelle in der CL\-Befehlszeile genannt werden, mit Ausnahme der **\/link**\-Option, die an letzter Stelle stehen muss.  Der Compiler beginnt mit den Optionen, die in der [CL\-Umgebungsvariablen](../../build/reference/cl-environment-variables.md) festgelegt wurden, und liest dann die Befehlszeile von links nach rechts. Befehlsdateien werden dabei in der angetroffenen Reihenfolge verarbeitet.  Jede Option wird auf alle Dateien in der Befehlszeile angewendet.  Wenn CL Optionen antrifft, die miteinander in Konflikt stehen, wird die am weitesten rechts stehende Option verwendet.  
  
## Siehe auch  
 [Syntax für die Compilerbefehlszeile](../../build/reference/compiler-command-line-syntax.md)