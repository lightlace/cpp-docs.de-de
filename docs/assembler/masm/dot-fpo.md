---
title: . FPO | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .FPO
dev_langs:
- C++
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df5185c0dc699764427989b2f46345d90ded1729
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="fpo"></a>.FPO
Die. FPO-Richtlinie steuert die Emissionen der Debug-Datensätze zum .debug$ F Segment oder Abschnitt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
FPO (  
cdwLocals  
,   
cdwParams  
,   
cbProlog  
,   
cbRegs  
,   
fUseBP  
,   
cbFrame  
)  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `cdwLocals`  
 Die Anzahl der lokalen Variablen, eine vorzeichenlose 32-Bit-Wert.  
  
 `cdwParams`  
 Die Größe der Parameter im DWORDS eine vorzeichenlose 16-Bit-Wert.  
  
 *cbProlog*  
 Anzahl der Bytes in der funktionsprologcodes einen nicht signierten 8-Bit-Wert.  
  
 `cbRegs`  
 Die Anzahl der Register gespeichert.  
  
 `fUseBP`  
 Gibt an, ob das EBP-Register zugeordnet wurde. 0 oder 1.  
  
 *cbFrame*  
 Gibt den Rahmentyp an.  Finden Sie unter [FPO_DATA](http://msdn.microsoft.com/library/windows/desktop/ms679352) für Weitere Informationen.  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)