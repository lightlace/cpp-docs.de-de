---
title: __inbytestring | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __inbytestring
- __inbytestring_cpp
dev_langs:
- C++
helpviewer_keywords:
- rep insb instruction
- __inbytestring intrinsic
ms.assetid: fe549556-e7a3-4af3-8ebf-8a7dc3cb233b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7f98ec84de71abe162d952f0d83a0b9005d5215d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="inbytestring"></a>__inbytestring
**Microsoft-spezifisch**  
  
 Liest Daten aus den angegebenen Port mit der `rep insb` Anweisung.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __inbytestring(  
   unsigned short Port,  
   unsigned char* Buffer,  
   unsigned long Count  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `Port`  
 Der Port, aus dem gelesen werden soll.  
  
 [out] `Buffer`  
 Die aus den Port gelesenen Daten werden hier geschrieben.  
  
 [in] `Count`  
 Die Anzahl der Bytes, der zu lesenden Daten.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__inbytestring`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Diese Routine ist nur als systeminterne Funktion verfügbar.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)