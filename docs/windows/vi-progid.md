---
title: Vi_progid | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.vi_progid
dev_langs:
- C++
helpviewer_keywords:
- vi_progid attribute
ms.assetid: a52449be-b93e-4111-b883-44bb8da53261
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 687a8a70d7f0a5381160a6515c80f6940cc0a434
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="viprogid"></a>vi_progid
Gibt eine versionsunabhängige Form der ProgID an.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ vi_progid(  
   name  
) ];  
```  
  
#### <a name="parameters"></a>Parameter  
 *name*  
 Die versionsunabhängige ProgID das Objekt darstellt.  
  
 Programm-IDs präsentieren eine lesbaren Version von den Klassenbezeichner (CLSID) verwendet, um COM/ActiveX-Objekte zu identifizieren.  
  
## <a name="remarks"></a>Hinweise  
 Die **Vi_progid** C++-Attribut ermöglicht die Angabe eine versionsunabhängige ProgID für ein COM-Objekt. Eine ProgID hat das Format *name1.name2.version*. Eine versionsunabhängige Programm-ID verfügt nicht über eine *Version*. Es ist möglich, beide geben die **progid** und **Vi_progid** Attribute auf einer Co-Klasse. Wenn Sie keinen angeben **Vi_progid**die versionsunabhängige Programm-ID ist der Wert von der [progid](../windows/progid.md) Attribut.  
  
 **Vi_progid** impliziert die **Co-Klasse** Attribut zu verwenden, d. h. bei Angabe von **Vi_progid**, ist dasselbe wie das Angeben der **Co-Klasse** und **Vi_progid** Attribute.  
  
 Die **Vi_progid** Attribut bewirkt, dass eine Klasse, unter dem angegebenen Namen automatisch registriert werden. Der generierten IDL-Datei wird keine den ProgID-Wert angezeigt.  
  
 Im ATL-Projekte Wenn die [Co-Klasse](../windows/coclass.md) Attribut ebenfalls vorhanden ist, wird durch die angegebene ProgID verwendet die **GetVersionIndependentProgID** Funktion (eingefügt, indem die **Co-Klasse** Attribut "").  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter der [Coclass](../windows/coclass.md) Beispiel für ein Beispiel für die Verwendung von **Vi_progid**.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union- und Struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
 [Schlüssel progID](http://msdn.microsoft.com/library/windows/desktop/dd542719)   
