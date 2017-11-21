---
title: . FPO | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .FPO
dev_langs: C++
helpviewer_keywords: .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fc26358e1da11ada6b23364576bfedb379bc4030
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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