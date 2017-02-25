---
title: "Ressourcencompiler: Schwerwiegender Fehler RC1020 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC1020"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1020"
ms.assetid: 3e073ebf-9136-4bf8-ac6a-3c642ed64594
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ressourcencompiler: Schwerwiegender Fehler RC1020
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unerwartetes "\#endif"  
  
 Die `#endif`\-Direktive wurde ohne eine der entsprechende Direktiven `#if`, **\#ifdef** oder **\#ifndef** verwendet.  
  
 Stellen Sie sicher, dass ein zugehöriges `#endif` für jede der Anweisungen `#if`, **\#ifdef** und **\#ifndef** vorhanden ist.