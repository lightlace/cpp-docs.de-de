---
title: Exitcodes von NMAKE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, exit codes
- exit codes
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e71442e1e36dbd69afa65051cbf08f403bf8b31
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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