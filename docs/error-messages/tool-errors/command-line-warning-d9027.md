---
title: Befehlszeilenwarnung D9027 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9027
dev_langs:
- C++
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dfe2493290c4e4cc5b744136b8e7036c6559220a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33301449"
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