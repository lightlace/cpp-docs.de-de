---
title: TLBID | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- tlbid
dev_langs:
- C++
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 52cb9237537e151e699974fe91c5a7a99725513f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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