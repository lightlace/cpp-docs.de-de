---
title: Fall (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.case
dev_langs:
- C++
helpviewer_keywords:
- case attribute
ms.assetid: 6fb883c3-0526-4932-a901-b4564dcaeb7d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 30d665861688054a4f6b7491f449014afe646c71
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860956"
---
# <a name="case-c"></a>case (C++)
Verwendet die [Switch_type](../windows/switch-type.md) Attribut in einer **Union**.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ case(  
   value  
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 *Wert*  
 Eine mögliche Eingabewert für den Sie verarbeiten möchten. Der Typ des **Wert** kann eine der folgenden Typen:  
  
-   `int`  
  
-   `char`  
  
-   `boolean`  
  
-   `enum`  
  
 oder ein Bezeichner eines solchen Typs.  
  
## <a name="remarks"></a>Hinweise  
 Die **Fall** C++-Attribut hat die gleiche Funktionalität wie die **Fall** MIDL-Attribut. Dieses Attribut wird nur verwendet, mit der [Switch_type](../windows/switch-type.md) Attribut.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code veranschaulicht die Verwendung der der **Fall** Attribut:  
  
```  
// cpp_attr_ref_case.cpp  
// compile with: /LD  
#include <unknwn.h>  
[export]  
struct SizedValue2 {  
   [switch_type(char), switch_is(kind)] union {  
      [case(1), string]  
          wchar_t* wval;  
      [default, string]  
          char* val;  
   };  
    char kind;  
};  
[module(name="ATLFIRELib")];  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Mitglied einer **Klasse** oder `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union- und Struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
