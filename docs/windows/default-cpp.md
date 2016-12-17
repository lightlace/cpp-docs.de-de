---
title: "default (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.default"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Standardattribut"
  - "Attribute [C#], default-Attribut"
  - "Standardwerte, default-Attribut"
ms.assetid: 0cdca716-1ba8-46d7-9399-167e55492870
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# default (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass die benutzerdefinierte Schnittstelle oder Disp\-Schnittstelle innerhalb einer Co\-Klasse die Standard\-Programmierschnittstelle darstellt.  
  
## Syntax  
  
```  
  
[ default(  
interface1  
,  
   interface2  
) ]  
  
```  
  
#### Parameter  
 *interface1*  
 Die Standardschnittstelle, die für Skriptumgebungen verfügbar gemacht wird, die ein Objekt auf Grundlage der Klasse erstellen, die mit dem **default**\-Attribut definiert ist.  
  
 Wenn keine Standardschnittstelle angegeben wird, wird das erste Vorkommen einer Nicht\-Quellschnittstelle als Standard verwendet.  
  
 *interface2*\(optional\)  
 Die Standard\-Quellschnittstelle. Sie müssen diese Schnittstelle auch beim [source](../windows/source-cpp.md)\-Attribut angeben.  
  
 Wenn keine Standard\-Quellschnittstelle angegeben ist, wird die erste Quellschnittstelle als Standard verwendet.  
  
## Hinweise  
 Das C\+\+\-Attribut **default** hat die gleiche Funktion wie das MIDL\-Attribut [default](http://msdn.microsoft.com/library/windows/desktop/aa366787). Das **default**\-Attribut wird auch mit dem [case](../windows/case-cpp.md)\-Attribut verwendet.  
  
## Beispiel  
 Der folgende Code zeigt, wie **default** bei der Definition einer Co\-Klasse verwendet wird, um **ICustomDispatch** als Standard\-Programmierschnittstelle anzugeben:  
  
```  
// cpp_attr_ref_default.cpp  
// compile with: /LD  
#include "windows.h"  
[module(name="MyLibrary")];  
  
[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustom {  
   HRESULT Custom([in] long l, [out, retval] long *pLong);  
};  
  
[dual, uuid("9E66A291-4365-11D2-A997-00C04FA37DDB")]   
__interface IDual {  
   HRESULT Dual([in] long l, [out, retval] long *pLong);  
};  
  
[object, uuid("9E66A293-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustomDispatch : public IDispatch {  
   HRESULT Dispatch([in] long l, [out, retval] long *pLong);  
};  
  
[   coclass,  
   default(ICustomDispatch),   
   source(IDual),  
   uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")  
]  
class CClass : public ICustom, public IDual, public ICustomDispatch {  
   HRESULT Custom(long l, long *pLong) { return(S_OK); }  
   HRESULT Dual(long l, long *pLong) { return(S_OK); }  
   HRESULT Dispatch(long l, long *pLong) { return(S_OK); }  
};  
  
int main() {  
#if 0 // Can't instantiate without implementations of IUnknown/IDispatch  
   CClass *pClass = new CClass;  
  
   long llong;  
  
   pClass->custom(1, &llong);  
   pClass->dual(1, &llong);  
   pClass->dispinterface(1, &llong);  
   pClass->dispatch(1, &llong);  
  
   delete pClass;  
#endif  
   return(0);  
}  
```  
  
 Das [source](../windows/source-cpp.md)\-Attribut weist außerdem ein Beispiel zum Verwenden von **default** auf.  
  
## Anforderungen  
  
### Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**class**, `struct`, Datenelement|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**coclass** \(bei Anwendung auf **class** oder `struct`\)|  
|**Ungültige Attribute**|Keine|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [coclass](../windows/coclass.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)