---
title: HelpContext | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpcontext
dev_langs:
- C++
helpviewer_keywords:
- helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2089bca316fb37304765ac14475b73cadaf79342
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39571359"
---
# <a name="helpcontext"></a>helpcontext
Gibt eine Kontext-ID, mit dem die Benutzerinformationen zu diesem Element in der Hilfedatei.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ helpcontext(  
   id  
) ]  
```  
  
### <a name="parameters"></a>Parameter  
 *ID*  
 Die Kontext-ID des Hilfethemas. Finden Sie unter [HTML-Hilfe: kontextbezogene Hilfe für Programme](../mfc/html-help-context-sensitive-help-for-your-programs.md) Weitere Informationen zum Kontext-IDs.  
  
## <a name="remarks"></a>Hinweise  
 Die **Helpcontext** C++-Attribut hat die gleiche Funktionalität wie die [Helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [Defaultvalue](../windows/defaultvalue.md) ein Beispiel zur Verwendung für **Helpcontext**.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Schnittstelle**, **Typedef**, **Klasse**, Methode, Eigenschaft|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Schnittstellenattribut](../windows/interface-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
 [Methodenattribute](../windows/method-attributes.md)   
 [TypeDef, Enum, Union- und Struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   
 [HelpFile](../windows/helpfile.md)   
 [helpstring](../windows/helpstring.md)   