---
title: Schwerwiegender Fehler C1905 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1905
dev_langs:
- C++
helpviewer_keywords:
- C1905
ms.assetid: fefc6769-477f-45a2-9878-6f0a5f42472c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d15bf00432cab6900c252d85cd642c414bdbbb22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1905"></a>Schwerwiegender Fehler C1905
Front-End und Back-End sind nicht kompatibel (müssen auf denselben Prozessor ausgerichtet sein).  
  
 Dieser Fehler tritt auf, wenn eine OBJ-Datei von einem Compiler-Front-End (C1.dll) generiert wird, das auf einen Prozessor abzielt, beispielsweise x86, ARM oder [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], jedoch von einem Back-End (C2.dll) für einen anderen Zielprozessor gelesen wird.  
  
 Stellen Sie zur Behebung dieses Problems sicher, dass Front-End und Back-End kompatibel sind. Dies ist die Standardeinstellung für Projekte, die in Visual Studio erstellt wurden. Dieser Fehler kann auftreten, wenn Sie die Projektdatei bearbeitet und dabei verschiedene Pfade zu den Compilertools verwendet haben. Wenn Sie den Pfad für die Compilertools nicht ausdrücklich festgelegt haben, kann dieser Fehler auftreten, wenn die Visual Studio-Installation beschädigt ist. Beispielsweise können Sie Compiler-DLL-Dateien von einem Speicherort zu einem anderen kopiert haben. Verwendung **Programme und Funktionen** in der Windows-Systemsteuerung reparieren oder neu installieren von Visual Studio.