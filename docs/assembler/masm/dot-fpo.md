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
ms.workload: cplusplus
ms.openlocfilehash: 61d9209b5cf817d89e9e017626222a9cc73e209e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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