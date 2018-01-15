---
title: Helpstringcontext | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.helpstringcontext
dev_langs: C++
helpviewer_keywords: helpstringcontext attribute [C++]
ms.assetid: d4cd135e-d91c-4aa3-9353-8aeb096f52cf
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3c5492d18085d78e20d6654898a6c66647e3bbe0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="helpstringcontext"></a>helpstringcontext
Gibt die ID des Hilfethemas in einer HLP oder CHM-Datei an.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ helpstringcontext(  
   contextID  
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 `contextID`  
 Eine 32-Bit-Hilfekontextbezeichner in der Hilfedatei.  
  
## <a name="remarks"></a>Hinweise  
 Die **Helpstringcontext** C++-Attribut hat die gleiche Funktionalität wie die [Helpstringcontext](http://msdn.microsoft.com/library/windows/desktop/aa366858) ODL-Attribut.  
  
## <a name="example"></a>Beispiel  
  
```  
// cpp_attr_ref_helpstringcontext.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[   object,   
   helpstring("help string"),   
   helpstringcontext(1),   
   uuid="11111111-1111-1111-1111-111111111111"  
]  
__interface IMyI   
{  
   HRESULT xx();  
};  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `interface`,-Schnittstellenmethode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Schnittstellenattribut](../windows/interface-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
 [Methodenattribut](../windows/method-attributes.md)   
 [Modul](../windows/module-cpp.md)   
