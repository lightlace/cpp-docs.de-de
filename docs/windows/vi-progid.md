---
title: Vi_progid | Microsoft-Dokumentation
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
ms.openlocfilehash: a812317f66df3c0b1a330808a58753abb890765c
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014051"
---
# <a name="viprogid"></a>vi_progid
Gibt eine Art versionsunabhängige Programm-ID an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
[ vi_progid(  
   name  
) ];  
```  
  
### <a name="parameters"></a>Parameter  
 *name*  
 Die versionsunabhängigen-ProgID, die das Objekt darstellt.  
  
 Versionsabhängige Programm-IDs präsentieren eine lesbaren Version von den Klassenbezeichner (CLSID) verwendet, um COM/ActiveX-Objekte zu identifizieren.  
  
## <a name="remarks"></a>Hinweise  
 Die **Vi_progid** C++-Attribut können Sie eine versionsunabhängige ProgID eines COM-Objekts angeben. Eine ProgID hat das Format *name1.name2.version*. Eine versionsunabhängige Programm-ID verfügt nicht über eine *Version*. Es ist möglich, beide geben die `progid` und **Vi_progid** Attribute einer `coclass`. Wenn Sie keinen angeben **Vi_progid**, wird die versionsunabhängige Programm-ID ist der Wert von der [progid](../windows/progid.md) Attribut.  
  
 **Vi_progid** impliziert die `coclass` -Attributs, d. h. Wenn Sie angeben, **Vi_progid**, es ist dasselbe wie beim Angeben der `coclass` und **Vi_progid** Attribute.  
  
 Die **Vi_progid** Attribut bewirkt, dass eine Klasse automatisch unter dem angegebenen Namen registriert werden. Der generierten IDL-Datei wird den ProgID-Wert nicht angezeigt werden.  
  
 In ATL-Projekte Wenn die [Co-Klasse](../windows/coclass.md) Attribut ebenfalls vorhanden ist, wird durch die angegebene ProgID verwendet die `GetVersionIndependentProgID` Funktion (eingefügt, indem die `coclass` Attribut).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter den [Co-Klasse](../windows/coclass.md) Beispiel für ein Beispiel für die Verwendung von **Vi_progid**.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, **Struktur**|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union- und Struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
 [Programm-ID-Schlüssel](http://msdn.microsoft.com/library/windows/desktop/dd542719)   