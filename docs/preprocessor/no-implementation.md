---
title: No_implementation | Microsoft-Dokumentation
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
ms.openlocfilehash: c882a8d4eb2510969401b4280eb66116ad220c77
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440835"
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
 
[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)