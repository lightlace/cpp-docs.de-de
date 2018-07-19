---
title: Embedded_idl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- embedded_idl
dev_langs:
- C++
helpviewer_keywords:
- embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e0b594952e8e5be0a9be9c843877c8c4bb95eca
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33842715"
---
# <a name="embeddedidl"></a>embedded_idl
**C++-spezifisch**  
  
 Gibt an, dass die Typbibliothek in die TLH-Datei geschrieben wird und der vom Attribut generierte Code beibehalten wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
embedded_idl[("param")]  
```  
  
#### <a name="parameters"></a>Parameter  
 `param`  
 Kann einer von zwei Werten sein:  
  
-   emitidl: Typinformationen, die von typelib importiert werden, sind in der IDL-Datei vorhanden, die für das attributierte Projekt generiert wird.  Dies ist die Standardeinstellung, die aktiv ist, wenn Sie keinen Parameter für `embedded_idl` angeben.  
  
-   no_emitidl: Typinformationen, die von typelib importiert werden, sind nicht in der IDL-Datei vorhanden, die für das attributierte Projekt generiert wird.  
  
## <a name="example"></a>Beispiel  
  
```  
// import_embedded_idl.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib2")];  
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")  
```  
  
## <a name="remarks"></a>Hinweise  
 **Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [#import-Direktive](../preprocessor/hash-import-directive-cpp.md)