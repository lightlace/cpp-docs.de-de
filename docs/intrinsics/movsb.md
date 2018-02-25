---
title: __movsb | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __movsb
dev_langs:
- C++
helpviewer_keywords:
- movsb instruction
- rep movsb instruction
- __movsb intrinsic
ms.assetid: ba5469f6-f797-4cd2-bee8-74c7666c26d4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 801de3d2c117d6ace73add6842c2729e5cb5f6ce
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="movsb"></a>__movsb
**Microsoft-spezifisch**  
  
 Generiert eine Zeichenfolge zu verschieben (`rep movsb`) Anweisung.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __movsb(   
   unsigned char* Destination,   
   unsigned const char* Source,   
   size_t Count   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `Destination`  
 Ein Zeiger auf das Ziel des Kopiervorgangs.  
  
 [in] `Source`  
 Ein Zeiger auf die Quelle der Kopie.  
  
 [in] `Count`  
 Die Anzahl der zu kopierenden Bytes.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__movsb`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Das Ergebnis ist, die die erste `Count` Bytes verweist `Source` kopiert werden, um die `Destination` Zeichenfolge.  
  
 Diese Routine ist nur als systeminterne Funktion verfügbar.  
  
## <a name="example"></a>Beispiel  
  
```  
// movsb.cpp  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__movsb)  
  
int main()  
{  
    unsigned char s1[100];  
    unsigned char s2[100] = "A big black dog.";  
    __movsb(s1, s2, 100);  
  
    printf_s("%s %s", s1, s2);  
}  
```  
  
```Output  
A big black dog. A big black dog.  
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)