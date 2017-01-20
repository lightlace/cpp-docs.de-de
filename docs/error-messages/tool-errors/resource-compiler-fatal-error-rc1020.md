---
title: "Ressourcencompiler: Schwerwiegender Fehler RC1020"
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
  - "RC1020"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1020"
ms.assetid: 3e073ebf-9136-4bf8-ac6a-3c642ed64594
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Ressourcencompiler: Schwerwiegender Fehler RC1020
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unerwartetes "\#endif"  
  
 Die `#endif`\-Direktive wurde ohne eine der entsprechende Direktiven `#if`, **\#ifdef** oder **\#ifndef** verwendet.  
  
 Stellen Sie sicher, dass ein zugehöriges `#endif` für jede der Anweisungen `#if`, **\#ifdef** und **\#ifndef** vorhanden ist.