---
title: MMWORD | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- MMWORD
dev_langs:
- C++
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e97b1e58116d633519b1a780928e05862ac1771d
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32054779"
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