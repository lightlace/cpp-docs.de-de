---
title: Library_block | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.library_block
dev_langs:
- C++
helpviewer_keywords:
- library_block attribute
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dbd97897138edffba12baf47d64465b1f6ca0df4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877890"
---
# <a name="libraryblock"></a>library_block
Fügt ein Konstrukt in der IDL-Bibliothek-Block vor.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
[library_block]  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie ein Konstrukt in den bibliotheksblock platzieren, stellen Sie sicher, dass er Sie übergeben wird, in der Typbibliothek, unabhängig davon, ob die Funktion verwiesen wird. Standardmäßig nur Konstrukte geändert, indem die [Coclass](../windows/coclass.md), [Dispinterface](../windows/dispinterface.md), und [Idl_module](../windows/idl-module.md) Attribute werden in den bibliotheksblock platziert.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Code wird eine benutzerdefinierte Schnittstelle innerhalb des Blocks Bibliothek platziert.  
  
```  
// cpp_attr_ref_library_block.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib")];  
[object, library_block, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface IMyInterface {  
   HRESULT f1();  
};  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Überall|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Compilerattribute](../windows/compiler-attributes.md)   
 [Eigenständige Attribute](../windows/stand-alone-attributes.md)   
