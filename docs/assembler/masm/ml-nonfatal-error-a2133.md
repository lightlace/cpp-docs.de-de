---
title: ML nicht schwerwiegende Fehler A2133 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2133
dev_langs:
- C++
helpviewer_keywords:
- A2133
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f240ed6f2e8330017e56334dfcc41be478537c7b
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32056206"
---
# <a name="ml-nonfatal-error-a2133"></a>Nicht schwerwiegender ML-Fehler A2133
**Registrieren von INVOKE überschrieben Wert**  
  
 Ein Registers wurde als Argument an eine Prozedur übergeben, aber der Code generiert, indem [INVOKE](../../assembler/masm/invoke.md) , andere Argumente übergeben, zerstört den Inhalt des Registers.  
  
 Der AX, AL AH, EAX, DX, DL, DH und EDX-Registern können vom Assembler verwendet werden, zum Ausführen der Datenkonvertierung.  
  
 Verwenden Sie einen anderen registrieren.  
  
## <a name="see-also"></a>Siehe auch  
 [ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)