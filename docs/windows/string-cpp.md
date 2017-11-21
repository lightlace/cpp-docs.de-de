---
title: Zeichenfolge (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.string
dev_langs: C++
helpviewer_keywords: string attribute
ms.assetid: ddde900a-2e99-4fcd-86e8-57e1bdba7c93
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0293785b9552b2e5696b9334e81aebf44c3bc4b7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="string-c"></a>string (C++)
Gibt an, dass das eindimensionale `char`, `wchar_t`, **Byte** (oder gleichwertigen) Array oder der Zeiger auf ein solches Array als Zeichenfolge behandelt werden muss.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
[string]  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **Zeichenfolge** C++-Attribut hat die gleiche Funktionalität wie die [Zeichenfolge](http://msdn.microsoft.com/library/windows/desktop/aa367270) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie Sie **Zeichenfolge** in einer Schnittstelle und auf eine Typdefinition:  
  
```  
// cpp_attr_ref_string.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
[export, string] typedef char a[21];  
[dispinterface, restricted, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl  
{  
   [id(1)] HRESULT Method3([in, string] char *pC);  
};  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Array oder Zeiger auf ein Array, Schnittstellenparameter, Schnittstellen-Methode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keine|  
|**Ungültige Attribute**|Keine|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Arrayattribute](../windows/array-attributes.md)   
 [export](../windows/export.md)   
