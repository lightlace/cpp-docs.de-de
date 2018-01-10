---
title: Satype | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.satype
dev_langs: C++
helpviewer_keywords: satype attribute
ms.assetid: 1716590b-6bcb-4aba-b1bc-82f7335f02c3
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9d4e083cfd0ee1a72992d3c400c4790f5cd50396
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="satype"></a>satype
Gibt den Datentyp, der die **SAFEARRAY** Struktur.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ satype(  
   data_type  
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 *data_type*  
 Der Datentyp für die **SAFEARRAY** Datenstruktur, die als Parameter an eine Schnittstellenmethode übergeben wird.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Parameter, für die Schnittstellen-Methode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
## <a name="remarks"></a>Hinweise  
 Die **Satype** C++-Attribut gibt den Datentyp, der die **SAFEARRAY**.  
  
> [!NOTE]
>  Eine Dereferenzierungsebene aus gelöscht wird die **SAFEARRAY** Zeiger in der generierten IDL-Datei aus, wie sie in der CPP-Datei deklariert ist.  
  
## <a name="example"></a>Beispiel  
  
```  
// cpp_attr_ref_satype.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyModule")];  
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]  
__interface A {  
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);  
};  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Compilerattribute](../windows/compiler-attributes.md)   
 [Parameterattribute](../windows/parameter-attributes.md)   
 [Methodenattribut](../windows/method-attributes.md)   
 [ID](../windows/id.md)   
