---
title: Schwerwiegender Fehler C1081 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1081
dev_langs:
- C++
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b5ea18ff3f2714d9621d4372cf541be2f9b225a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1081"></a>Schwerwiegender Fehler C1081
'Symbol': Dateiname zu lang  
  
 Ein Pfadname länger `_MAX_PATH` (definiert durch STDLIB.h als 260 Zeichen enthalten). Kürzen Sie den Namen der Datei an.  
  
 Beim Aufruf von CL.exe mit einem kurzen Dateinamen muss der Compiler u. u. einen vollständigen Pfadnamen zu generieren. Beispielsweise `cl -c myfile.cpp` kann dazu führen, dass den Compiler generiert:  
  
```  
D:\<very-long-directory-path>\myfile.cpp  
```