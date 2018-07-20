---
title: Threading (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.threading
dev_langs:
- C++
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f21ea8c16b4e09a5ad1845a10797be00f91b0d8f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891323"
---
# <a name="threading-c"></a>threading (C++)
Gibt das Threadingmodell für ein COM-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ threading(  
   model=enumeration  
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 ***Modell*** (optional)  
 Einer der folgenden Threadingmodelle:  
  
-   **Apartment** (Apartmentthreading für Anwendungen)  
  
-   **neutrale** (.NET Framework-Komponenten ohne Benutzeroberfläche)  
  
-   **einzelne** (einfache threading)  
  
-   **Kostenlose** (threading freizugeben)  
  
-   **beide** (Apartment und Freethreadings)  
  
 Der Standardwert ist **Apartment**.  
  
## <a name="remarks"></a>Hinweise  
 Die **threading** C++-Attribut nicht in der generierten IDL-Datei angezeigt, aber in der Implementierung des COM-Objekts verwendet werden.  
  
 Im ATL-Projekte Wenn die [Co-Klasse](../windows/coclass.md) Attribut vorhanden ist, wird das Threadingmodell gemäß *Modell* wird als der Vorlagenparameter übergeben der [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) Klasse , eingefügt, indem die **Coclass** Attribut.  
  
 Die **threading** Attribut schützt auch Zugriff auf eine [Event_source](../windows/event-source.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter der [lizenziert](../windows/licensed.md) Beispiel für ein Beispiel für die Verwendung von **threading**.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**coclass**|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [COM-Attribute](../windows/com-attributes.md)   
 [TypeDef, Enum, Union- und Struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
 [Multithreadingunterstützung für älteren Code (Visual C++)](../parallel/multithreading-support-for-older-code-visual-cpp.md)   
 [Neutrale Apartments](http://msdn.microsoft.com/library/windows/desktop/ms681813)   
