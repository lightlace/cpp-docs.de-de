---
title: "Schwerwiegender Fehler C1905"
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
  - "C1905"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1905"
ms.assetid: fefc6769-477f-45a2-9878-6f0a5f42472c
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1905
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Front\-End und Back\-End sind nicht kompatibel \(müssen auf denselben Prozessor ausgerichtet sein\).  
  
 Dieser Fehler tritt auf, wenn eine OBJ\-Datei von einem Compiler\-Front\-End \(C1.dll\) generiert wird, das auf einen Prozessor abzielt, beispielsweise x86, ARM oder [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], jedoch von einem Back\-End \(C2.dll\) für einen anderen Zielprozessor gelesen wird.  
  
 Stellen Sie zur Behebung dieses Problems sicher, dass Front\-End und Back\-End kompatibel sind.  Dies ist die Standardeinstellung für Projekte, die in Visual Studio erstellt wurden.  Dieser Fehler kann auftreten, wenn Sie die Projektdatei bearbeitet und dabei verschiedene Pfade zu den Compilertools verwendet haben.  Wenn Sie den Pfad für die Compilertools nicht ausdrücklich festgelegt haben, kann dieser Fehler auftreten, wenn die Visual Studio\-Installation beschädigt ist.  Beispielsweise können Sie Compiler\-DLL\-Dateien von einem Speicherort zu einem anderen kopiert haben.  Mit **Programme und Funktionen** in der Windows\-Systemsteuerung können Sie Visual Studio reparieren oder neu installieren.