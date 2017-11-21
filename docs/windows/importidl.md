---
title: Importidl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.importidl
dev_langs: C++
helpviewer_keywords: importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8842141b1c6e8159023da9a7cc486e81460ef36b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="importidl"></a>importidl
Fügt die angegebenen IDL-Datei in der generierten IDL-Datei an.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ importidl(  
   idl_file  
) ];  
```  
  
#### <a name="parameters"></a>Parameter  
 `idl_file`  
 Identifiziert den Namen der IDL-Datei, die Sie mit der IDL-Datei, die generiert wird, und für Ihre Anwendung zusammenführen möchten.  
  
## <a name="remarks"></a>Hinweise  
 Die **Importidl** C++-Attribut wird im Abschnitt außerhalb des Blocks für die Bibliothek (in `idl_file`) in der generierten IDL-Datei des Programms und die Bibliothekabschnitt (in `idl_file`) in der Bibliothek Teil des Programms generierten IDL-Datei.  
  
 Sie verwenden möchten **Importidl**, z. B. Wenn Sie eine handcodierten IDL-Datei mit der generierten IDL-Datei verwenden möchten.  
  
## <a name="example"></a>Beispiel  
  
```  
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
|**Erforderliche Attribute**|Keine|  
|**Ungültige Attribute**|Keine|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Compilerattribute](../windows/compiler-attributes.md)   
 [Eigenständige Attribute](../windows/stand-alone-attributes.md)   
 [Importieren](../windows/import.md)   
 [importlib](../windows/importlib.md)   
 [einschließen](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   
