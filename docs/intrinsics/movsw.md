---
title: __movsw | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __movsw
dev_langs: C++
helpviewer_keywords:
- movsw instruction
- rep movsw instruction
- __movsw intrinsic
ms.assetid: db402ad5-7f0e-449a-b0b0-eea9928d6435
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7a5660a72eaa612721c956e68ae829148d353dc9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="movsw"></a>__movsw
**Microsoft-spezifisch**  
  
 Generiert eine Zeichenfolge zu verschieben (`rep movsw`) Anweisung.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __movsw(   
   unsigned short* Dest,   
   unsigned short* Source,   
   size_t Count   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `Dest`  
 Das Ziel des Vorgangs.  
  
 [in] `Source`  
 Die Quelle des Vorgangs.  
  
 [in] `Count`  
 Die Anzahl der Wörter zu kopieren.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__movsw`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Das Ergebnis ist, die die erste `Count` Wörter verweist `Source` kopiert werden, um die `Dest` Zeichenfolge.  
  
 Diese Routine ist nur als systeminterne Funktion verfügbar.  
  
## <a name="example"></a>Beispiel  
  
```  
// movsw.cpp  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__movsw)  
  
int main()  
{  
    unsigned short s1[10];  
    unsigned short s2[10] = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
    __movsw(s1, s2, 10);  
  
    for (int i = 0; i < 10; i++)  
        printf_s("%d ", s1[i]);  
    printf_s("\n");  
}  
```  
  
```Output  
0 1 2 3 4 5 6 7 8 9   
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)