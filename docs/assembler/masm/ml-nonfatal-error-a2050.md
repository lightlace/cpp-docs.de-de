---
title: ML-Schwerwiegender Fehler A2050 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A2050
dev_langs: C++
helpviewer_keywords: A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a51a90f294afd0347057efb04ab37ce790532ba4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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