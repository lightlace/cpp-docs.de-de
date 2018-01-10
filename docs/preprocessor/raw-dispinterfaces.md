---
title: Raw_dispinterfaces | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: raw_dispinterfaces
dev_langs: C++
helpviewer_keywords: raw_dispinterfaces attribute
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3d92c6940c4eabc83143ce1054604ae4648347d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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