---
title: "einschließen (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.include
dev_langs: C++
helpviewer_keywords: include attribute
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 31d56b56b104473ffe3edbcf8672aa8b5a92243d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="include-c"></a>include (C++)
Gibt einen oder mehrere Headerdateien, in der generierten IDL-Datei eingeschlossen werden sollen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ include(  
   header_file  
) ];  
```  
  
#### <a name="parameters"></a>Parameter  
 *HEADER_FILE*  
 Der Name einer Datei, die Sie möchten in der generierten IDL-Datei enthalten.  
  
## <a name="remarks"></a>Hinweise  
 Die **enthalten** C++-Attribut bewirkt, dass ein `#include` Anweisung unten versetzt werden die `import "docobj.idl"` -Anweisung in der generierten IDL-Datei.  
  
 Die **enthalten** C++-Attribut hat die gleiche Funktionalität wie die [enthalten](http://msdn.microsoft.com/library/windows/desktop/aa367052) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt ein Beispiel zur Verwendung **enthalten**. In diesem Beispiel enthält die Datei include.h nur eine #include-Anweisung.  
  
```  
// cpp_attr_ref_include.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[include(cpp_attr_ref_include.h)];  
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
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Eigenständige Attribute](../windows/stand-alone-attributes.md)   
 [Importieren](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [includelib](../windows/includelib-cpp.md)   
 [importlib](../windows/importlib.md)   
