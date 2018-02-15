---
title: MMWORD | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- MMWORD
dev_langs:
- C++
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0570a55dc11994e12acedb85d3ae8015abefb54c
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="mmword"></a>MMWORD
Für 64-Bit-multimedia-Operanden mit MMX- und SSE (XMM)-Anweisungen verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
MMWORD  
```  
  
## <a name="remarks"></a>Hinweise  
 `MMWORD` ist ein Typ.  Vor dem MMWORD MASM hinzugefügt wird konnte entsprechende Funktionalität mit erreicht wurden:  
  
```  
mov mm0, qword ptr [ebx]  
```  
  
 Zwar beide Anweisungen in 64-Bit-Operanden, funktioniert `QWORD` ist der Typ für 64-Bit-Ganzzahlen ohne Vorzeichen und `MMWORD` ist der Typ für einen 64-Bit-multimedia-Wert.  
  
 `MMWORD` Dient zur Darstellung der vom selben Typs wie [__m64](../../cpp/m64.md).  
  
## <a name="example"></a>Beispiel  
  
```  
movq     mm0, mmword ptr [ebx]  
```