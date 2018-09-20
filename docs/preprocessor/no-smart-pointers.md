---
title: No_smart_pointers | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_search_pointers
dev_langs:
- C++
helpviewer_keywords:
- no_smart_pointers attribute
ms.assetid: d69dd71e-08a8-4446-a3d0-a062dc29cb17
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a01e6cf423aece9fba74c4b81fa247d57844e107
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439886"
---
# <a name="nosmartpointers"></a>no_smart_pointers
**C++-spezifisch**  
  
Unterdrückt die Erstellung von intelligenten Zeigern für alle Schnittstellen in der Typbibliothek.  
  
## <a name="syntax"></a>Syntax  
  
```  
no_smart_pointers  
```  
  
## <a name="remarks"></a>Hinweise  
 
Wenn Sie `#import` verwenden, rufen Sie standardmäßig die Deklaration eines intelligenten Zeigers für alle Schnittstellen in der Typbibliothek ab. Diese intelligenten Zeiger sind vom Typ [_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md).  
  
**Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 
[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)