---
title: COM_INTERFACE_ENTRY (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.com_interface_entry
dev_langs:
- C++
helpviewer_keywords:
- com_interface_entry attribute
ms.assetid: 10368f81-b99b-4a0f-ba4f-a142e6911a5c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b0fb7de1987d77f19e04f867aac68cbcc67c1f1e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="cominterfaceentry-c"></a>com_interface_entry (C++)
Fügt einen Eintrag Schnittstelle in der Zielklasse der COM-Zuordnung.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
     [ com_interface_entry(   
  com_interface_entry  
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 *COM_INTERFACE_ENTRY*  
 Eine Zeichenfolge mit den tatsächlichen Text des Eintrags. Eine Liste der möglichen Werte finden Sie unter [COM_INTERFACE_ENTRY Makros](../atl/reference/com-interface-entry-macros.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `com_interface_entry` C++-Attribut fügt den ungekürzt Inhalt einer Zeichenfolge in die Zuordnung des COM-Schnittstelle des Zielobjekts. Wenn das Attribut angewendet wird, sobald auf das Zielobjekt der Eintrag in der Anfang des vorhandenen schnittstellenzuordnung eingefügt wird. Wenn das Attribut mehrmals auf dasselbe Zielobjekt angewendet wird, werden die Einträge am Anfang der schnittstellenzuordnung in der Reihenfolge eingefügt, die sie empfangen werden.  
  
 Dieses Attribut erfordert, dass die Attribute [coclass](../windows/coclass.md), [progid](../windows/progid.md), oder [vi_progid](../windows/vi-progid.md) (oder ein anderes Attribut, das eines der genannten impliziert) auch auf demselben Element angewendet werden. Wenn ein einzelnes Attribut verwendet wird, werden die anderen beiden automatisch angewendet. Wenn z.B. **progid** angewendet wird, werden **vi_progid** und **coclass** ebenso angewendet.  
  
 Da der ersten Verwendung des `com_interface_entry` bewirkt, dass die neue Schnittstelle, um am Anfang der schnittstellenzuordnung eingefügt werden muss es sich um eine der folgenden COM_INTERFACE_ENTRY-Typen:  
  
-   COM_INTERFACE_ENTRY  
  
-   COM_INTERFACE_ENTRY_IID  
  
-   COM_INTERFACE_ENTRY2  
  
-   COM_INTERFACE_ENTRY2_IID  
  
 Zusätzliche Verwendungen von der `com_interface_entry` Attribut kann alle unterstützte COM_INTERFACE_ENTRY-Typen verwenden.  
  
 Diese Einschränkung ist notwendig, da den ersten Eintrag in die schnittstellenzuordnung von ATL als Identität verwendet **IUnknown**daher der Eintrag muss eine gültige Schnittstelle sein. Im folgenden Codebeispiel ist beispielsweise ungültig, da der erste Eintrag in die schnittstellenzuordnung eine tatsächliche COM-Schnittstelle nicht angegeben ist.  
  
```  
[ coclass, com_interface_entry =  
    "COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"  
]  
   class CMyClass  
   {  
   };  
```  
  
## <a name="example"></a>Beispiel  
 Der folgende Code fügt zwei Einträge auf der vorhandenen COM-schnittstellenzuordnung der **CMyBaseClass**. Die erste ist eine standard-Schnittstelle, und die zweite Blendet die **IDebugTest** Schnittstelle.  
  
```  
// cpp_attr_ref_com_interface_entry.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name ="ldld")];  
  
[ object,  
  uuid("7dbebed3-d636-4917-af62-c767a720a5b9")]  
__interface IDebugTest{};  
  
[ object,  
  uuid("2875ceac-f94b-4087-8e13-d13dc167fcfc")]  
__interface IMyClass{};  
  
[ coclass,  
  com_interface_entry ("COM_INTERFACE_ENTRY (IMyClass)"),  
  com_interface_entry ("COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"),  
  uuid("b85f8626-e76e-4775-b6a0-4826a9e94af2")  
]  
  
class CMyClass: public IMyClass, public IDebugTest  
{  
};  
```  
  
 Der resultierende COM-Objekt-Zuordnung für **CMyBaseClass** lautet wie folgt:  
  
```  
BEGIN_COM_MAP(CMyClass)  
    COM_INTERFACE_ENTRY (IMyClass)  
    COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)  
    COM_INTERFACE_ENTRY(IMyClass)  
    COM_INTERFACE_ENTRY2(IDispatch, IMyClass)  
    COM_INTERFACE_ENTRY(IDebugTest)  
    COM_INTERFACE_ENTRY(IProvideClassInfo)  
END_COM_MAP()  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Ja|  
|**Erforderliche Attribute**|Ein Attribut oder mehrere Attribute der folgenden: **coclass**, **progid**, oder **vi_progid**.|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [COM-Attribute](../windows/com-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
 [typedef-, enum-, union- und struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   
