---
title: v1_enum | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.v1_enum
dev_langs:
- C++
helpviewer_keywords:
- v1_enum attribute
ms.assetid: 2fe92d92-81b9-4a1c-b6ce-437d0eb770ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b057ef891a00829fd64d967ffa860a66d6d49d5d
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40012341"
---
# <a name="v1enum"></a>v1_enum
Wird angewiesen, der angegebene enumerierten Typ als eine 32-Bit-Entität statt der 16-Bit-Standard übertragen werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
[v1_enum]  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **v1_enum** C++-Attribut hat die gleiche Funktionalität wie die [v1_enum](http://msdn.microsoft.com/library/windows/desktop/aa367303) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code veranschaulicht die Verwendung der **v1_enum**:  
  
```cpp  
// cpp_attr_ref_v1_enum.cpp  
// compile with: /LD  
[module(name="MyLibrary")];  
  
[export, v1_enum]   
enum eList {   
   e1 = 1,   
   e2 = 2  
};  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Enumerationstyp|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [typedef-, enum-, union- und struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   