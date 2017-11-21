---
title: Reservieren | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: allocate_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], allocate
- allocate __declspec keyword
ms.assetid: 67828b31-de60-4c0e-b0a6-ef3aab22641d
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 83f819338286139e2b03efd900c7dc6026f6895b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="allocate"></a>allocate
**Microsoft-spezifisch**  
  
 Die **zuordnen** deklarationsspezifizierer benennt ein Datensegment, in dem das Datenelement zugeordnet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
__declspec(allocate("  
segname  
")) declarator  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Name *Segname* muss mit einem der folgenden Pragmas deklariert werden:  
  
-   [code_seg](../preprocessor/code-seg.md)  
  
-   [const_seg](../preprocessor/const-seg.md)  
  
-   [data_seg](../preprocessor/data-seg.md)  
  
-   [init_seg](../preprocessor/init-seg.md)  
  
-   [section](../preprocessor/section.md)  
  
## <a name="example"></a>Beispiel  
  
```  
// allocate.cpp  
#pragma section("mycode", read)  
__declspec(allocate("mycode"))  int i = 0;  
  
int main() {  
}  
```  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [__declspec](../cpp/declspec.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)