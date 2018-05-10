---
title: Cpp_quote | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.cpp_quote
dev_langs:
- C++
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 38ecabcde55f49687abf7caff66fb2c316fab0fe
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="cppquote"></a>cpp_quote
Gibt die angegebene Zeichenfolge, ohne die Anführungszeichen in der generierten IDL-Datei aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ cpp_quote(  
   "statement"  
) ];  
```  
  
#### <a name="parameters"></a>Parameter  
 *statement*  
 Eine C#-Anweisung.  
  
## <a name="remarks"></a>Hinweise  
 Die **Cpp_quote** C++-Attribut ist nützlich, wenn Sie eine Präprozessordirektive in einer IDL-Datei aufnehmen möchten.  
  
 Sie können auch **Cpp_quote** und .h-Datei als Teil der Kompilierung MIDL generiert werden soll. Beispielsweise, wenn Sie eine C++-Headerdatei enthalten, die verwendet der C++-IDL-Attribute, aber verwenden Sie diese Datei kann nicht für eine Aufgabe, können Sie kompilieren es dann zum Erstellen einer MIDL-generierten h-Datei, die Sie verwenden sollten.  
  
 Die **Cpp_quote** Attribut hat die gleiche Funktionalität wie die [Cpp_quote](http://msdn.microsoft.com/library/windows/desktop/aa366765) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [duale](../windows/dual.md) verwenden Sie ein Beispiel für die Verwendung **Cpp_quote**.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Überall|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Eigenständige Attribute](../windows/stand-alone-attributes.md)   
