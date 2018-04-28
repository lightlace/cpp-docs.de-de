---
title: ML-Schwerwiegender Fehler A2050 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2050
dev_langs:
- C++
helpviewer_keywords:
- A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 159ed131c13166435114234b3b16a82cd4d41d1f
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="ml-nonfatal-error-a2050"></a>Nicht schwerwiegender ML-Fehler A2050
**Real oder BCD-Nummer nicht zulässig**  
  
 Eine Gleitkommazahl (real) oder Binary Coded Decimal (BCD)-Konstante wurde außer verwendet als einen Initialisierer Daten.  
  
 Eine der folgenden aufgetreten ist:  
  
-   Eine reelle Zahl oder einen BCD wurde in einem Ausdruck verwendet.  
  
-   Eine reelle Zahl wurde verwendet, um eine Direktive außer initialisieren [DWORD](../../assembler/masm/dword.md), [QWORD](../../assembler/masm/qword.md), oder [TBYTE](../../assembler/masm/tbyte.md).  
  
-   Eine BCD wurde verwendet, um eine Direktive außer initialisieren `TBYTE`.  
  
## <a name="see-also"></a>Siehe auch  
 [ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)