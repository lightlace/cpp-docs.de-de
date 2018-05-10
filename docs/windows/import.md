---
title: Importieren Sie | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.import
dev_langs:
- C++
helpviewer_keywords:
- import attribute
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b371cd1094a49f8a629cb6f8e880fd1210670f91
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="import"></a>import
Gibt eine andere IDL, ODL oder Header-Datei enthält Definitionen, die Sie von Ihrem wichtigsten IDL verweisen möchten.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ import(  
   idl_file  
) ];  
```  
  
#### <a name="parameters"></a>Parameter  
 `idl_file`  
 Der Name einer IDL-Datei, die in der Typbibliothek des aktuellen Projekts importiert werden sollen.  
  
## <a name="remarks"></a>Hinweise  
 Die **importieren** C++-Attribut bewirkt, dass ein `#import` Anweisung unten versetzt werden die `import "docobj.idl"` -Anweisung in der generierten IDL-Datei. Die **importieren** Attribut hat die gleiche Funktionalität wie die [importieren](http://msdn.microsoft.com/library/windows/desktop/aa367047) MIDL-Attribut.  
  
 Die **importieren** Attribut wird nur die angegebene Datei in der IDL-Datei, die vom Projekt; generiert werden, die **importieren** Attribut ist nicht möglich, die Konstrukte in der angegebenen Datei aus dem Quellcode aufrufen in Ihrem Projekt.  Um Konstrukte in der angegebenen Datei aus dem Quellcode in Ihrem Projekt aufrufen zu können, verwenden Sie entweder [#import](../preprocessor/hash-import-directive-cpp.md) und `embedded_idl` -Attribut, oder Sie können schließen die .h-Datei für die `idl_file`, wenn eine .h-Datei vorhanden ist.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code  
  
```  
// cpp_attr_ref_import.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[import(import.idl)];  
```  
  
 erzeugt den folgenden Code in der generierten IDL-Datei:  
  
```  
import "docobj.idl";  
import "import.idl";  
  
[ uuid(EED3644C-8488-3ECD-BA97-147DB3CDB499), version(1.0) ]  
library MyLib {  
   importlib("stdole2.tlb");  
   importlib("olepro32.dll");  
...  
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
 [importidl](../windows/importidl.md)   
 [importlib](../windows/importlib.md)   
 [Einschließen](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   
