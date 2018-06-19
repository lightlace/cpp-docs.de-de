---
title: TLBID | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- tlbid
dev_langs:
- C++
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d651546733f42b1a714ac7a39992fa2d392c8fa
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33839867"
---
# <a name="tlbid"></a>tlbid
**C++-spezifisch**  
  
 Ermöglicht das Laden anderer Bibliotheken als der primären Typbibliothek.  
  
## <a name="syntax"></a>Syntax  
  
```  
tlbid(number)  
```  
  
#### <a name="parameters"></a>Parameter  
 `number`  
 Die Nummer der Typbibliothek in `filename`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn mehrere Typbibliotheken in einer DLL zusammengefasst sind, können mit `tlbid` andere Bibliotheken als die primäre Typbibliothek geladen werden.  
  
 Zum Beispiel:  
  
```  
#import <MyResource.dll> tlbid(2)  
```  
  
 identisch mit folgendem Ausdruck:  
  
```  
LoadTypeLib("MyResource.dll\\2");  
```  
  
 **Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [#import-Direktive](../preprocessor/hash-import-directive-cpp.md)