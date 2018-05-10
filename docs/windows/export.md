---
title: Exportieren | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.export
dev_langs:
- C++
helpviewer_keywords:
- export attribute
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 67b71639fc0b7d0039f5665d2cc187191ac14baf
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="export"></a>"export"
Bewirkt, dass eine Datenstruktur, in der IDL-Datei abgelegt werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
[export]  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **exportieren** C++-Attribut bewirkt, dass eine Datenstruktur, die in der IDL-Datei abgelegt werden soll, und klicken Sie dann in der Typbibliothek in einem Binärformat kompatible Format zur Verfügung, die sie für die Verwendung mit einer beliebigen Sprache zur Verfügung stellt.  
  
 Können nicht angewendet werden die **exportieren** -Attribut auf eine Klasse, selbst wenn die Klasse nur öffentliche Member verfügt (das Äquivalent zu einer `struct`).  
  
 Wenn Sie die unbenannten exportieren `enum`s oder `struct`s, werden benannt, die mit **__unnamed *** X*, wobei *x* ist eine laufende Nummer.  
  
 Die Typdefinitionen für den Export gültig sind Basistypen, Strukturen, Unions, Enumerationen, oder geben die Bezeichner.  Finden Sie unter [Typedef](http://msdn.microsoft.com/library/windows/desktop/aa367287) für Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie Sie die **exportieren** Attribut:  
  
```  
// cpp_attr_ref_export.cpp  
// compile with: /LD  
[module(name="MyLibrary")];  
  
[export]  
struct MyStruct {  
   int i;  
};  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Union**, `typedef`, `enum`, `struct`, oder `interface`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Compilerattribute](../windows/compiler-attributes.md)   
 [typedef-, enum-, union- und struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   
