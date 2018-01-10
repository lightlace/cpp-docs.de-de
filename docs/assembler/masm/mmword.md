---
title: MMWORD | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MMWORD
dev_langs: C++
helpviewer_keywords: MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bbe20f842a97186071431cd73e7de65fa8170bd4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="mmword"></a>MMWORD
Für 64-Bit-multimedia-Operanden mit MMX- und SSE (XMM)-Anweisungen verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
MMWORD  
```  
  
## <a name="remarks"></a>Hinweise  
 `MMWORD`ist ein Typ.  Vor dem MMWORD MASM hinzugefügt wird konnte entsprechende Funktionalität mit erreicht wurden:  
  
```  
mov mm0, qword ptr [ebx]  
```  
  
 Zwar beide Anweisungen in 64-Bit-Operanden, funktioniert `QWORD` ist der Typ für 64-Bit-Ganzzahlen ohne Vorzeichen und `MMWORD` ist der Typ für einen 64-Bit-multimedia-Wert.  
  
 `MMWORD`Dient zur Darstellung der vom selben Typs wie [__m64](../../cpp/m64.md).  
  
## <a name="example"></a>Beispiel  
  
```  
movq     mm0, mmword ptr [ebx]  
```