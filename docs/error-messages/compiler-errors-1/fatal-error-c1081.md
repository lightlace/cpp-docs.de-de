---
title: Schwerwiegender Fehler C1081 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1081
dev_langs:
- C++
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 148e3e6035304eb155a478e5971defd9a0a55120
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1081"></a>Schwerwiegender Fehler C1081
'Symbol': Dateiname zu lang  
  
 Ein Pfadname länger `_MAX_PATH` (definiert durch STDLIB.h als 260 Zeichen enthalten). Kürzen Sie den Namen der Datei an.  
  
 Beim Aufruf von CL.exe mit einem kurzen Dateinamen muss der Compiler u. u. einen vollständigen Pfadnamen zu generieren. Beispielsweise `cl -c myfile.cpp` kann dazu führen, dass den Compiler generiert:  
  
```  
D:\<very-long-directory-path>\myfile.cpp  
```
