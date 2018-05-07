---
title: 'Ressourcencompiler: Schwerwiegender Fehler RW1025 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW1025
dev_langs:
- C++
helpviewer_keywords:
- RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ba216e63cb0cae92b4541800493a2fb6195553a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="resource-compiler-fatal-error-rw1025"></a>Ressourcencompiler: Schwerwiegender Fehler RW1025
Aus ganz Heapspeicher  
  
 Überprüfen Sie für Arbeitsspeicher-Software, die zu viel Speicherplatz beansprucht werden kann. Verwenden Sie das CHKDSK-Programm, um herauszufinden, wie viel Arbeitsspeicher, Sie haben.  
  
 Wenn Sie eine große Ressourcendatei erstellen, teilen Sie das Ressourcenskript in zwei Dateien. Verwenden Sie nach dem Erstellen zweier RES-Dateien, die MS-DOS-Befehlszeile, um ganz verbinden:  
  
```  
copy first.res /b + second.res /b full.res  
```