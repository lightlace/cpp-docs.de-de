---
title: Befehlszeilenwarnung D9026 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9026
dev_langs:
- C++
helpviewer_keywords:
- D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e2d99573ee46c51178cc2fe995fa0f526b800f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33299837"
---
# <a name="command-line-warning-d9026"></a>Befehlszeilenwarnung D9026
Optionen gelten für die gesamte Befehlszeile.  
  
 Nachdem ein Dateiname angegeben wurde, wurde eine Option für einen Befehl angegeben. Die Option wurde auf die Datei angewendet, das ihm vorausgeht.  
  
 Beispielsweise ist in den Befehl  
  
```  
CL verdi.c /G5 puccini.c  
```  
  
 die Datei VERDI.c wird mit der Option/G5 und nicht vom Standard/G4 kompiliert werden.  
  
 Dieses Verhalten unterscheidet sich von dem einiger früherer Versionen, die angewendet werden, nur die Optionen, die vor dem Dateinamen, wodurch VERDI.c angegeben, das kompiliert wird mit/G4 und wurden mithilfe von/G5 kompiliert wird.