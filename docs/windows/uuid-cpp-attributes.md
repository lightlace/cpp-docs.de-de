---
title: UUID (C++-Attribute) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.uuid
dev_langs:
- C++
helpviewer_keywords:
- uuid attribute
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e56793855b278e0631c39ebfcdc51669a001a24b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891531"
---
# <a name="uuid-c-attributes"></a>uuid (C++-Attribute)
Gibt die eindeutige ID für eine Klasse oder Schnittstelle an.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ uuid(  
   "uuid"  
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 *uuid*  
 Ein 128-Bit, eindeutigen Bezeichner.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Definition der eine Schnittstelle oder Klasse keine der `uuid` C++-Attribut, und klicken Sie dann auf Visual C++-Compilers bieten eine. Geben Sie bei einem `uuid`, Sie müssen die Anführungszeichen einschließen.  
  
 Wenn Sie keinen angeben `uuid`, generiert der Compiler dieselbe GUID für Schnittstellen oder Klassen mit dem gleichen Namen in verschiedenen Attribut Projekte auf einem Computer.  
  
 Uuidgen.exe oder Guidgen.exe können um Ihren eigenen eindeutigen IDs zu generieren. (Wenn eines dieser Tools ausführen möchten, klicken Sie auf **starten** , und klicken Sie auf **ausführen** auf das Menü. Geben Sie dann den Namen des Tools erforderlich.)  
  
 Wenn in einem Projekt verwendet, die nicht gleichzeitig ATL verwenden, geben an, die `uuid` Attribut entspricht der Angabe der [Uuid](../cpp/uuid-cpp.md) __declspec-Modifizierer. Zum Abrufen der `uuid` einer Klasse können Sie [__uuidof](../cpp/uuidof-operator.md)  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter der [bindbare](../windows/bindable.md) Beispiel für ein Beispiel für die Verwendung von `uuid`.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`, `interface`, **Union**, `enum`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Schnittstellenattribut](../windows/interface-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
 [TypeDef, Enum, Union- und Struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   
 [uuid](http://msdn.microsoft.com/library/windows/desktop/aa367302)   
