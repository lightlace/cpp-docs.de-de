---
title: Raw_dispinterfaces | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_dispinterfaces
dev_langs:
- C++
helpviewer_keywords:
- raw_dispinterfaces attribute
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1f2a0d91d0f0dd3d23886ade75072526e6c895f7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849453"
---
# <a name="rawdispinterfaces"></a>raw_dispinterfaces
**C++-spezifisch**  
  
 Weist den Compiler an, Wrapperfunktionen auf niedriger Ebene für Disp-Schnittstellenmethoden und Eigenschaften, die aufrufen generieren **IDispatch:: Invoke** und Zurückgeben der `HRESULT` Fehlercode.  
  
## <a name="syntax"></a>Syntax  
  
```  
raw_dispinterfaces  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn dieses Attribut nicht angegeben wird, werden nur Wrapper auf hoher Ebene generiert, die im Falle eines Fehlers C++-Ausnahmen auslösen.  
  
 **Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [#import-Direktive](../preprocessor/hash-import-directive-cpp.md)