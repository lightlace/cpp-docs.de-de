---
title: "Compilerfehler C3859 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3859"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3859"
ms.assetid: 40e93b25-4393-4467-90de-035434a665c7
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C3859
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Virtueller Speicherbereich für PCH wurde überschritten; kompilieren Sie erneut mit einer Befehlszeilenoption von '\-Zmvalue' oder größer  
  
 Ihr vorkompilierter Header ist zu klein für die Menge an Daten, die der Compiler versucht, einzufügen.  Verwenden Sie das Compilerkennzeichen **\/Zm**, um einen größeren Wert für die vorkompilierte Headerdatei anzugeben.  Weitere Informationen finden Sie unter [\/Zm \(Begrenzung der Speicherzuweisung für vorkompilierten Header festlegen\)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).