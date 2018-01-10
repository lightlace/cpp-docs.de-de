---
title: HelpFile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.helpfile
dev_langs: C++
helpviewer_keywords: helpfile attribute
ms.assetid: d75161c1-1363-4019-ae09-e7e3b8a3971e
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 63987b4e1427f12925b55fa3570d80b9e3a4686d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="helpfile"></a>helpfile
Legt den Namen der Hilfedatei für eine Typbibliothek.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ helpfile(  
   "filename"  
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 *filename*  
 Der Name der Datei, die die Hilfethemen enthält.  
  
## <a name="remarks"></a>Hinweise  
 Die **Helpfile** C++-Attribut hat die gleiche Funktionalität wie die [Helpfile](http://msdn.microsoft.com/library/windows/desktop/aa366853) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [Modul](../windows/module-cpp.md) ein Beispiel zum Verwenden von **Helpfile**.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|`interface`, `typedef`, **Klasse**, Methode, Eigenschaft|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Schnittstellenattribut](../windows/interface-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
 [Methodenattribut](../windows/method-attributes.md)   
 [TypeDef, Enum, Union- und Struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   
 [HelpContext](../windows/helpcontext.md)   
 [helpstring](../windows/helpstring.md)   
