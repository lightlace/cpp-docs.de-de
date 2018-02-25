---
title: No_dual_interfaces | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- no_dual_interfaces
dev_langs:
- C++
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ba20fcba43cc23dfce447d7e91955a43c28a6a31
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="nodualinterfaces"></a>no_dual_interfaces
**C++-spezifisch**  
  
 Ändert die Art, mit der der Compiler Wrapperfunktionen für Methoden der dualen Schnittstelle generiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
no_dual_interfaces  
```  
  
## <a name="remarks"></a>Hinweise  
 Normalerweise ruft der Wrapper die Methode über die virtuelle Funktionstabelle für die Schnittstelle auf. Mit `no_dual_interfaces`, ruft der Wrapper stattdessen **IDispatch:: Invoke** zum Aufrufen der Methode.  
  
 **Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [#import-Direktive](../preprocessor/hash-import-directive-cpp.md)