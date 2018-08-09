---
title: Importidl | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.importidl
dev_langs:
- C++
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1de680b2598a9439338986c283a4041482642fa0
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015757"
---
# <a name="importidl"></a>importidl
Fügt die angegebenen IDL-Datei in der generierten IDL-Datei an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
[ importidl(  
   idl_file  
) ];  
```  
  
### <a name="parameters"></a>Parameter  
 *idl_file*  
 Identifiziert den Namen der IDL-Datei, die mit der IDL-Datei, die generiert wird, und für Ihre Anwendung zusammengeführt werden sollen.  
  
## <a name="remarks"></a>Hinweise  
 Die **Importidl** C++-Attribut wird im Abschnitt außerhalb des bibliotheksblocks (in *Idl_file*) in der generierten IDL-Datei des Programms und die Bibliothekabschnitt (in *Idl_file*) in die Bibliothek Teil Ihres Programms IDL-Datei generiert.  
  
 Sie verwenden möchten **Importidl**, z. B. Wenn Sie eine handcodierten IDL-Datei mit der generierten IDL-Datei verwenden möchten.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// cpp_attr_ref_importidl.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[importidl("import.idl")];  
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
 [Importieren](../windows/import.md)   
 [importlib](../windows/importlib.md)   
 [einschließen](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   