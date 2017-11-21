---
title: Befehlszeilenwarnung D9027 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: D9027
dev_langs: C++
helpviewer_keywords: D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5ccdccbc4c6df8f948b44eeaa096cff46824d043
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="command-line-warning-d9027"></a>Befehlszeilenwarnung D9027
Quelldatei "\<Dateiname >' ignoriert  
  
 CL.exe ignoriert die Eingabequelle-Datei.  
  
 Diese Warnung kann durch ein Leerzeichen zwischen der/Fo-Option und eine Ausgabedatei in einer Befehlszeile mit der Option/c verursacht werden. Zum Beispiel:  
  
```  
cl /c /Fo output.obj input.c   
```  
  
 Da ein Leerzeichen zwischen/FO und `output.obj`, CL.exe akzeptiert `output.obj` als den Namen der Eingabedatei. Um das Problem zu beheben, entfernen Sie den Speicherplatz:  
  
```  
cl /c /Fooutput.obj input.c   
```