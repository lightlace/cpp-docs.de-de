---
title: Schwerwiegender Fehler C1208 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1208
dev_langs:
- C++
helpviewer_keywords:
- C1208
ms.assetid: 4eefd8f0-5c2e-4a11-9e63-293e1139db65
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b5c2a03c6e8f0ee018a7e3b3449fc0448d179be
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1208"></a>Schwerwiegender Fehler C1208
Das Zuordnen von Verweisklassen im Stapel wird von der installierten Laufzeitversion nicht unterstützt.  
  
 C1208 tritt auf, wenn Sie einen Compiler der aktuellen Version, aber eine Common Language Runtime (CLR) einer früheren Version verwenden.  
  
 Bestimmte Funktionen des Compilers funktionieren möglicherweise nicht in einer früheren Version der Laufzeit.  
  
 Installieren Sie die CLR-Version, die für die Verwendung mit dem Compiler vorgesehen ist.