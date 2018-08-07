---
title: Helpstringcontext | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpstringcontext
dev_langs:
- C++
helpviewer_keywords:
- helpstringcontext attribute [C++]
ms.assetid: d4cd135e-d91c-4aa3-9353-8aeb096f52cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 16f113610beb4c6427af5627ea8dfd725e02600d
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569998"
---
# <a name="helpstringcontext"></a>helpstringcontext
Gibt die ID des Hilfethemas in eine .hlp oder CHM-Datei an.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ helpstringcontext(  
   contextID  
) ]  
```  
  
### <a name="parameters"></a>Parameter  
 *contextID*  
 Eine 32-Bit-Hilfekontextbezeichner in der Hilfedatei.  
  
## <a name="remarks"></a>Hinweise  
 Die **Helpstringcontext** C++-Attribut hat die gleiche Funktionalität wie die [Helpstringcontext](http://msdn.microsoft.com/library/windows/desktop/aa366858) ODL-Attribut.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
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
|**Betrifft**|**Klasse**, **Schnittstelle**,-Schnittstellenmethode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Schnittstellenattribut](../windows/interface-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
 [Methodenattribute](../windows/method-attributes.md)   
 [Modul](../windows/module-cpp.md)   