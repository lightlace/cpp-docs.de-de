---
title: __outdwordstring | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __outdwordstring
dev_langs: C++
helpviewer_keywords:
- outsd instruction
- __outdwordstring intrinsic
- rep outsd instruction
ms.assetid: 55b31a65-aab7-4b5c-b61d-d9e2fb0c497a
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 974964f49c776f687a9c0e928be218be6c8fa335
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="outdwordstring"></a>__outdwordstring
**Microsoft-spezifisch**  
  
 Generiert die `rep outsd` -Anweisung, die sendet `Count` Doppelwort beginnenden `Buffer` Ausgang von angegebenen e/a- `Port`.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __outdwordstring(   
   unsigned short Port,   
   unsigned long* Buffer,   
   unsigned long Count   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `Port`  
 Der Port, an die die Daten gesendet werden soll.  
  
 [in] `Buffer`  
 Ein Zeiger auf die Daten auf den angegebenen Port gesendet werden.  
  
 [in] `Count`  
 Die Anzahl der Doppelwort senden.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__outdwordstring`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Diese Routine ist nur als systeminterne Funktion verfügbar.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)