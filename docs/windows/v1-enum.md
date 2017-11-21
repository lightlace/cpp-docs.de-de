---
title: v1_enum | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.v1_enum
dev_langs: C++
helpviewer_keywords: v1_enum attribute
ms.assetid: 2fe92d92-81b9-4a1c-b6ce-437d0eb770ca
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 93c11fec97b5ee239bfd929974c09709811837ff
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="v1enum"></a>v1_enum
Weist der angegebene enumerierten Typ als eine 32-Bit-Entität statt der 16-Bit-Standard übertragen werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
[v1_enum]  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **v1_enum** C++-Attribut hat die gleiche Funktionalität wie die [v1_enum](http://msdn.microsoft.com/library/windows/desktop/aa367303) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code veranschaulicht die Verwendung der **v1_enum**:  
  
```  
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
|**Erforderliche Attribute**|Keine|  
|**Ungültige Attribute**|Keine|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [typedef-, enum-, union- und struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   
