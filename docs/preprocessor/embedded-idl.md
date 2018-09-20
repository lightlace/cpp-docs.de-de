---
title: Das Embedded_idl | Microsoft-Dokumentation
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
ms.openlocfilehash: 9ad4a58cf02522eb7ca1c00055c73ff921e92b11
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386118"
---
# <a name="embeddedidl"></a>embedded_idl
**C++-spezifisch**  
  
Gibt an, dass die Typbibliothek in die TLH-Datei geschrieben wird und der vom Attribut generierte Code beibehalten wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
embedded_idl[("param")]  
```  
  
### <a name="parameters"></a>Parameter  
*param*  
Kann einer von zwei Werten sein:  
  
- emitidl: Typinformationen, die von typelib importiert werden, sind in der IDL-Datei vorhanden, die für das attributierte Projekt generiert wird.  Dies ist die Standardeinstellung, die aktiv ist, wenn Sie keinen Parameter für `embedded_idl` angeben.  
  
- no_emitidl: Typinformationen, die von typelib importiert werden, sind nicht in der IDL-Datei vorhanden, die für das attributierte Projekt generiert wird.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// import_embedded_idl.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib2")];  
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")  
```  
  
## <a name="remarks"></a>Hinweise  
 
**Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 
[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)