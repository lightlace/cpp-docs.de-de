---
title: Nonbrowsable | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.nonbrowsable
dev_langs: C++
helpviewer_keywords: nonbrowsable attribute
ms.assetid: e71a98e7-4b65-454a-9829-342b9f2a84be
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e4b5cd632f3d84af72c59cc647128f93eb829670
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="nonbrowsable"></a>nonbrowsable
Gibt an, dass ein Schnittstellenmember nicht in einem Eigenschaftenbrowser angezeigt werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
[nonbrowsable]  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **Nonbrowsable** C++-Attribut hat die gleiche Funktionalität wie die [Nonbrowsable](http://msdn.microsoft.com/library/windows/desktop/aa367117) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
  
```  
// cpp_attr_ref_nonbrowsable.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[object, helpstring("help string"), helpstringcontext(1),   
uuid="11111111-1111-1111-1111-111111111111"]   
__interface IMyI  
{  
   [nonbrowsable] HRESULT xx();  
};  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Schnittstellenmethode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keine|  
|**Ungültige Attribute**|Keine|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Methodenattribut](../windows/method-attributes.md)   
