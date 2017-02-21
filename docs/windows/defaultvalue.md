---
title: "defaultvalue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.defaultvalue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "defaultvalue attribute"
ms.assetid: efa5d050-b2cc-4d9e-9b8e-79954f218d3a
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# defaultvalue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ermöglicht die Angabe eines Standardwerts einen typisierten optionalen Parameter zu.  
  
## Syntax  
  
```  
  
[ defaultvalue= value ]  
```  
  
#### Parameter  
 *Wert*  
 Der Standardwert für den Parameter.  
  
## Hinweise  
 Das Attribut **defaultvalue** C\+\+ verfügt über die gleichen Funktionen wie das [defaultvalue](http://msdn.microsoft.com/library/windows/desktop/aa366793) MIDL\-Attribut.  
  
## Beispiel  
 Im folgenden Code wird eine Schnittstellenmethode mit dem **defaultvalue**\-Attributs an:  
  
```  
// cpp_attr_ref_defaultvalue.cpp  
// compile with: /LD  
#include <windows.h>  
  
[export] typedef long HRESULT;  
[export, ptr, string] typedef unsigned char * MY_STRING_TYPE;  
  
[  uuid("479B29EE-9A2C-11D0-B696-00A0C903487A"),  
   dual, oleautomation,  
   helpstring("IFireTabCtrl Interface"),  
   helpcontext(122), pointer_default(unique) ]  
  
__interface IFireTabCtrl : IDispatch {  
   [bindable, propget] HRESULT get_Size([out, retval, defaultvalue("33")] long *nSize);  
   [bindable, propput] HRESULT put_Size([in] int nSize);  
};  
  
[ module(name="ATLFIRELib", uuid="479B29E1-9A2C-11D0-B696-00A0C903487A",  
      version="1.0", helpstring="ATLFire 1.0 Type Library") ];  
```  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|Schnittstellen Parametern|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [out](../windows/out-cpp.md)   
 [retval](../windows/retval.md)   
 [in](../windows/in-cpp.md)   
 [pointer\_default](../windows/pointer-default.md)   
 [unique](../windows/unique-cpp.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)