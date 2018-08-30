---
title: . FPO | Microsoft-Dokumentation
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
ms.openlocfilehash: 234ec5bd703a390d1e2ee60e48d99d346d4aad95
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203112"
---
# <a name="fpo"></a>.FPO
Die. FPO-Richtlinie steuert die Ausgabe der Compilerdiagnose eines Debug-Datensätze zum .debug$ F-Segment oder Abschnitt.  
  
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
 Die Größe der Parameter in DWORDS, eine vorzeichenlose 16-Bit-Wert.  
  
 *cbProlog*  
 Anzahl der Bytes im Prolog Funktionscode, eine vorzeichenlose 8-Bit-Wert.  
  
 `cbRegs`  
 Anzahl der gespeicherten Register.  
  
 `fUseBP`  
 Gibt an, ob das EBP-Register zugeordnet wurde. 0 oder 1.  
  
 *cbFrame*  
 Gibt den Rahmentyp.  Finden Sie unter [FPO_DATA](/windows/desktop/api/winnt/ns-winnt-_fpo_data) für Weitere Informationen.  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)