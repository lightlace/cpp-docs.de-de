---
title: . STAPEL | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- .STACK
dev_langs:
- C++
helpviewer_keywords:
- .STACK directive
ms.assetid: 70019463-5d4f-41b6-8464-023a8ac2466f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 140afd2edc8a0cdb540adc7e12bf97662d5d6084
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="stack"></a>.STACK
Bei Verwendung mit [. Modell](../../assembler/masm/dot-model.md), definiert einen Zeitabschnitt Stapel (mit Segmentnamen Stapel). Das optionale `size` gibt die Anzahl der Bytes für den Stapel (Standard 1.024). Die `.STACK` Richtlinie schließt automatisch die Stack-Anweisung.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
.STACK [[size]]  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)