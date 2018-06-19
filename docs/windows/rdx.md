---
title: RDX | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.rdx
dev_langs:
- C++
helpviewer_keywords:
- rdx attribute
ms.assetid: ff8e4312-c1ad-4934-bdaa-86f54409651e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7647ca56e3159564826efa9caf438456b9ae3568
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878956"
---
# <a name="rdx"></a>rdx
Erstellt einen Registrierungsschlüssel oder ändert einen vorhandenen Registrierungsschlüssel.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ rdx(   
   key,   
   valuename=NULL,   
   regtype   
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 `key`  
 Der Name des Schlüssels erstellt oder geöffnet werden.  
  
 `valuename`(optional)  
 Gibt das Wertfeld "festgelegt werden. Wenn ein Wertfeld mit diesem Namen im Schlüssel nicht bereits vorhanden ist, wird er hinzugefügt.  
  
 *regtype*  
 Der Typ des Registrierungsschlüssels, der hinzugefügt wird. Kann einen der folgenden sein: **Text**, **Dword**, **binäre**, oder `CString`.  
  
## <a name="remarks"></a>Hinweise  
 Die **Rdx** C++-Attribut erstellt oder ändert einen vorhandenen Registrierungsschlüssel für eine COM-Komponente. Das Attribut hinzugefügt das Objekt, das das Ziel-Element implementiert ein Makro BEGIN_RDX_MAP. `RegistryDataExchange`, eine Funktion, die als Ergebnis das Makro BEGIN_RDX_MAP eingefügten zum Übertragen von Daten zwischen der Registrierung und die Datenmember verwendet werden können  
  
 Dieses Attribut kann verwendet werden, zusammen mit den [Coclass](../windows/coclass.md), [progid](../windows/progid.md), oder [Vi_progid](../windows/vi-progid.md) Attribute oder andere Attribute, die eine der folgenden impliziert.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse** oder `struct` Member|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Code Fügt einen Registrierungsschlüssel namens MyValue an das System, beschreibt die CMyClass COM-Komponente.  
  
```  
// cpp_attr_ref_rdx.cpp  
// compile with: /LD /link /OPT:NOREF  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
  
[module (name="MyLib")];  
  
class CMyClass {  
public:  
   CMyClass() {  
      strcpy_s(m_sz, "SomeValue");  
   }  
  
   [ rdx(key = "HKCR\\MyApp.MyApp.1", valuename = "MyValue", regtype = "text")]   
   char m_sz[256];  
};  
```  
  
## <a name="see-also"></a>Siehe auch  
 [COM-Attribute](../windows/com-attributes.md)   
 [registration_script](../windows/registration-script.md)   
