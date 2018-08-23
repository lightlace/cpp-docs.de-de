---
title: TLBID | Microsoft-Dokumentation
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
ms.openlocfilehash: 1ec0150e63209728cf2f02c854fe03702b8a45b4
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2018
ms.locfileid: "42539598"
---
# <a name="tlbid"></a>tlbid
**C++-spezifisch**  
  
Ermöglicht das Laden anderer Bibliotheken als der primären Typbibliothek.  
  
## <a name="syntax"></a>Syntax  
  
```  
tlbid(number)  
```  
  
### <a name="parameters"></a>Parameter  
*Anzahl*  
Die Nummer der Typbibliothek in `filename`.  
  
## <a name="remarks"></a>Hinweise  
 
Wenn mehrere Typbibliotheken in einer DLL, es ist möglich, beim Laden von Bibliotheken als die primäre Typbibliothek mit basieren **Tlbid**.  
  
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
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)