---
title: No_implementation | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_implementation
dev_langs:
- C++
helpviewer_keywords:
- no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf756a411404d2ebb821d5b226818844acfca75b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849547"
---
# <a name="noimplementation"></a>no_implementation
**C++-spezifisch**  
  
 Unterdrückt die Generierung des TLI-Headers, der die Implementierungen der Wrappermemberfunktionen enthält.  
  
## <a name="syntax"></a>Syntax  
  
```  
no_implementation  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn dieses Attribut festgelegt ist, wird der TLH-Header mit den Deklarationen zur Bereitstellung von Typbibliothekselementen ohne eine `#include`-Anweisung zur Einbindung der TLI-Headerdatei generiert.  
  
 Dieses Attribut wird verwendet, in Verbindung mit [Implementation_only](../preprocessor/implementation-only.md).  
  
 **Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [#import-Direktive](../preprocessor/hash-import-directive-cpp.md)