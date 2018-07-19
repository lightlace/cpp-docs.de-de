---
title: __faststorefence | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __faststorefence_cpp
- __faststorefence
dev_langs:
- C++
helpviewer_keywords:
- __faststorefence intrinsic
- sfence instruction
ms.assetid: 6c6eb973-3cf0-4306-b3af-cfde9b0210a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f8c4a343126a14e1aea931b1e154714af280904
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33327797"
---
# <a name="faststorefence"></a>__faststorefence
**Microsoft-spezifisch**  
  
 Stellt sicher, dass jeder vorhergehende Speicherverweis, einschließlich Speicherverweisen zum Laden und Speichern, vor jedem nachfolgenden Speicherverweis global sichtbar ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __faststorefence();  
```  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__faststorefence`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Erzeugt eine Anweisungssequenz für eine Arbeitsspeicherbarriere für den gesamten Arbeitsspeicher, die sicherstellt, dass Lade- und Speichervorgänge, die vor dem systeminternen Vorgang ausgegeben wurden, global sichtbar sind, bevor die Ausführung fortgesetzt wird. Die Wirkung ist mit dem systeminternen `_mm_mfence` auf allen x64-Plattformen vergleichbar, aber schneller.  
  
 Auf der AMD64-Plattform generiert diese Routine eine Anweisung, die eine Speicherumgrenzung schneller erstellt als die `sfence`-Anweisung. Verwenden Sie bei zeitkritischem Code diese systeminterne Anweisung anstelle von `_mm_sfence` nur auf AMD64-Plattformen. Auf Intel x64-Plattformen ist die `_mm_sfence`-Anweisung schneller.  
  
 Diese Routine ist nur als systeminterne Funktion verfügbar.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)