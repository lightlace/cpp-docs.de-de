---
title: ML nicht schwerwiegende Fehler A2133 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- A2133
dev_langs:
- C++
helpviewer_keywords:
- A2133
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: adc1929f14b5264717936f1a4aebb8dabd2e439d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="ml-nonfatal-error-a2133"></a>Nicht schwerwiegender ML-Fehler A2133
**Registrieren von INVOKE überschrieben Wert**  
  
 Ein Registers wurde als Argument an eine Prozedur übergeben, aber der Code generiert, indem [INVOKE](../../assembler/masm/invoke.md) , andere Argumente übergeben, zerstört den Inhalt des Registers.  
  
 Der AX, AL AH, EAX, DX, DL, DH und EDX-Registern können vom Assembler verwendet werden, zum Ausführen der Datenkonvertierung.  
  
 Verwenden Sie einen anderen registrieren.  
  
## <a name="see-also"></a>Siehe auch  
 [ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)