---
title: Exportieren Sie | Microsoft-Dokumentation
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
ms.openlocfilehash: ad5f886c4d475cb51b370ae25549387f191ab4b6
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39653130"
---
# <a name="export"></a>"export"
Bewirkt, dass eine Datenstruktur, in der IDL-Datei platziert wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
[export]  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **exportieren** C++-Attribut bewirkt, dass eine Datenstruktur, die in der IDL-Datei platziert werden und dann in der Typbibliothek in eine Binärdatei-kompatiblen Format zur Verfügung, die sie für die Verwendung mit einer beliebigen Sprache zur Verfügung stellt.  
  
 Können nicht angewendet werden die **exportieren** -Attribut auf eine Klasse, auch wenn die Klasse nur öffentliche Member hat (das Äquivalent einer **Struktur**).  
  
 Wenn Sie unbenannte exportieren **Enum**s oder **Struktur**s, werden sie erhalten ihre Namen auf, die mit beginnen **__unnamed *** X*, wobei *x* ist eine sequenzielle Anzahl.  
  
 Die Typdefinitionen für den Export gültig sind, Basistypen, Strukturen, Unions, Enumerationen, oder geben Bezeichner.  Finden Sie unter [Typedef](http://msdn.microsoft.com/library/windows/desktop/aa367287) für Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie Sie mit der **exportieren** Attribut:  
  
```cpp  
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
|**Betrifft**|**Union**, **Typedef**, **Enum**, **Struktur**, oder **Schnittstelle**|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Compilerattribute](../windows/compiler-attributes.md)   
 [typedef-, enum-, union- und struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   