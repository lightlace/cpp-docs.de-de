---
title: Importlib | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.importlib
dev_langs: C++
helpviewer_keywords: importlib attribute
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 27c74785f56d7cb339eff25a645191ece1e14b32
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="importlib"></a>importlib
Stellt Typen, die bereits in einer anderen Typbibliothek kompiliert wurden, der erstellten Typbibliothek zur Verfügung.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ importlib(  
   "tlb_file"  
) ];  
```  
  
#### <a name="parameters"></a>Parameter  
 *tlb_file*  
 Der Name einer TLB-Datei in Anführungszeichen, die in die Typbibliothek des aktuellen Projekts importiert werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Die **Importlib** C++-Attribut bewirkt, dass ein `importlib` Anweisung in den bibliotheksblock der generierten IDL-Datei abgelegt werden soll. Die **Importlib** Attribut hat die gleiche Funktionalität wie die [Importlib](http://msdn.microsoft.com/library/windows/desktop/aa367050) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt ein Beispiel zur Verwendung **Importlib**:  
  
```  
// cpp_attr_ref_importlib.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[importlib("importlib.tlb")];  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Überall|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keine|  
|**Ungültige Attribute**|Keine|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Compilerattribute](../windows/compiler-attributes.md)   
 [Eigenständige Attribute](../windows/stand-alone-attributes.md)   
 [Importieren](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [einschließen](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)