---
title: Exitcodes von NMAKE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, exit codes
- exit codes
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 13cbe4806d8b3960cbf80df41c7cce6e7657ba7e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="exit-codes-from-nmake"></a>Exitcodes von NMAKE
Die folgenden Exitcodes von NMAKE zurückgegeben:  
  
|Code|Bedeutung|  
|----------|-------------|  
|0|Kein Fehler (möglicherweise eine Warnung)|  
|1|Unvollständige Build (ausgegeben, wenn/k verwendet wird)|  
|2|Programmfehler, möglicherweise aufgrund eines der folgenden:|  
||– Ein Syntaxfehler in Makefiles|  
||-Ein Fehler oder Beendigung Statuscode von einem Befehl|  
||-Eine Unterbrechung durch den Benutzer|  
|4|Systemfehler:: nicht genügend Arbeitsspeicher|  
|255|Ziel ist nicht aktuell (wird nur bei der/q / ausgegeben)|  
  
## <a name="see-also"></a>Siehe auch  
 [Ausführen von NMAKE](../build/running-nmake.md)