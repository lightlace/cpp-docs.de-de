---
title: . STAPEL | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .STACK
dev_langs: C++
helpviewer_keywords: .STACK directive
ms.assetid: 70019463-5d4f-41b6-8464-023a8ac2466f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 20557bf243db1c004d6ec62dcb589cfb8605a285
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="stack"></a>.STACK
Bei Verwendung mit [. Modell](../../assembler/masm/dot-model.md), definiert einen Zeitabschnitt Stapel (mit Segmentnamen Stapel). Das optionale `size` gibt die Anzahl der Bytes für den Stapel (Standard 1.024). Die `.STACK` Richtlinie schließt automatisch die Stack-Anweisung.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
.STACK [[size]]  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)