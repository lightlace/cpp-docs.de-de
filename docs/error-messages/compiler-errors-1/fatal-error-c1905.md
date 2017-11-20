---
title: Schwerwiegender Fehler C1905 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1905
dev_langs:
- C++
helpviewer_keywords:
- C1905
ms.assetid: fefc6769-477f-45a2-9878-6f0a5f42472c
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9d1662b05764500d0ac6a96119f865294cac260b
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="fatal-error-c1905"></a>Schwerwiegender Fehler C1905
Front-End und Back-End sind nicht kompatibel (müssen auf denselben Prozessor ausgerichtet sein).  
  
 Dieser Fehler tritt auf, wenn eine OBJ-Datei von einem Compiler-Front-End (C1.dll) generiert wird, das auf einen Prozessor abzielt, beispielsweise x86, ARM oder [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], jedoch von einem Back-End (C2.dll) für einen anderen Zielprozessor gelesen wird.  
  
 Stellen Sie zur Behebung dieses Problems sicher, dass Front-End und Back-End kompatibel sind. Dies ist die Standardeinstellung für Projekte, die in Visual Studio erstellt wurden. Dieser Fehler kann auftreten, wenn Sie die Projektdatei bearbeitet und dabei verschiedene Pfade zu den Compilertools verwendet haben. Wenn Sie den Pfad für die Compilertools nicht ausdrücklich festgelegt haben, kann dieser Fehler auftreten, wenn die Visual Studio-Installation beschädigt ist. Beispielsweise können Sie Compiler-DLL-Dateien von einem Speicherort zu einem anderen kopiert haben. Verwendung **Programme und Funktionen** in der Windows-Systemsteuerung reparieren oder neu installieren von Visual Studio.