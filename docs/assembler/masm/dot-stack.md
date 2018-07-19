---
title: . STAPEL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .STACK
dev_langs:
- C++
helpviewer_keywords:
- .STACK directive
ms.assetid: 70019463-5d4f-41b6-8464-023a8ac2466f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dab47677da8db2afca73a078b110300a017e7c8d
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32052299"
---
# <a name="stack"></a>.STACK
Bei Verwendung mit [. Modell](../../assembler/masm/dot-model.md), definiert einen Zeitabschnitt Stapel (mit Segmentnamen Stapel). Das optionale `size` gibt die Anzahl der Bytes für den Stapel (Standard 1.024). Die `.STACK` Richtlinie schließt automatisch die Stack-Anweisung.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
.STACK [[size]]  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)