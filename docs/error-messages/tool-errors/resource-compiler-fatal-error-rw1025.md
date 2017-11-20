---
title: 'Ressourcencompiler: Schwerwiegender Fehler RW1025 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RW1025
dev_langs: C++
helpviewer_keywords: RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d6e8b8ced110b13b65d91f968e476b5d20cf93c9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="resource-compiler-fatal-error-rw1025"></a>Ressourcencompiler: Schwerwiegender Fehler RW1025
Aus ganz Heapspeicher  
  
 Überprüfen Sie für Arbeitsspeicher-Software, die zu viel Speicherplatz beansprucht werden kann. Verwenden Sie das CHKDSK-Programm, um herauszufinden, wie viel Arbeitsspeicher, Sie haben.  
  
 Wenn Sie eine große Ressourcendatei erstellen, teilen Sie das Ressourcenskript in zwei Dateien. Verwenden Sie nach dem Erstellen zweier RES-Dateien, die MS-DOS-Befehlszeile, um ganz verbinden:  
  
```  
copy first.res /b + second.res /b full.res  
```