---
title: "Reihenfolge von CL-Optionen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe-Compiler, Festlegen von Optionen"
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Reihenfolge von CL-Optionen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Optionen können an beliebiger Stelle in der CL\-Befehlszeile genannt werden, mit Ausnahme der **\/link**\-Option, die an letzter Stelle stehen muss.  Der Compiler beginnt mit den Optionen, die in der [CL\-Umgebungsvariablen](../../build/reference/cl-environment-variables.md) festgelegt wurden, und liest dann die Befehlszeile von links nach rechts. Befehlsdateien werden dabei in der angetroffenen Reihenfolge verarbeitet.  Jede Option wird auf alle Dateien in der Befehlszeile angewendet.  Wenn CL Optionen antrifft, die miteinander in Konflikt stehen, wird die am weitesten rechts stehende Option verwendet.  
  
## Siehe auch  
 [Syntax für die Compilerbefehlszeile](../../build/reference/compiler-command-line-syntax.md)