---
title: "CVTRES: Schwerwiegender Fehler CVT1100"
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
  - "CVT1100"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CVT1100"
ms.assetid: 886e88dd-5818-4b5f-84f2-d2a3d75f0aaf
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# CVTRES: Schwerwiegender Fehler CVT1100
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Doppelte Ressource \- Typ:type, Name:name, Sprache:language, Flags:flags, Größe:size  
  
 Die angegebene Ressource wurde mehrmals festgelegt.  
  
 Dieser Fehler tritt auf, wenn der Linker eine Typbibliothek erstellt, [\/TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md) nicht angegeben wurde, und eine Ressource im Projekt bereits 1 verwendet.  Geben Sie in diesem Fall "\/TLBID" und eine andere Zahl bis 65.535 an.