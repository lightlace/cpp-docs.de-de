---
title: "import"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.import"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "import attribute"
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# import
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt ein weiteres .idl, .odl oder Headerdatei, die Definitionen enthält, die Sie in der Main IDL verweisen möchten.  
  
## Syntax  
  
```  
  
      [ import(  
   idl_file  
) ];  
```  
  
#### Parameter  
 `idl_file`  
 Der Name einer IDL\-Datei, importierte in die Typbibliothek des aktuellen Projekts.  
  
## Hinweise  
 Das Attribut **Import** C\+\+ wird eine `#import` unterhalb der Anweisung `import "docobj.idl"`\-Anweisung in der generierten IDL\-Datei abgelegt werden soll.  Das **Import**\-Attribut verfügt über die gleichen Funktionen wie das [Import](http://msdn.microsoft.com/library/windows/desktop/aa367047) MIDL\-Attribut.  
  
 Das Attribut wird nur **Import** die angegebene Datei in die IDL\-Datei, die vom Projekt generiert wird. **Import** das Attribut können Sie keine Konstrukte in der angegebenen Datei aus dem Quellcode im Projekt aufrufen.  Um Konstrukte in der angegebenen Datei aus dem Quellcode im Projekt aufzurufen, entweder Verwendung [\#import](../preprocessor/hash-import-directive-cpp.md) und das `embedded_idl`\-Attribut oder Sie können die H\-Datei für `idl_file`umfassen, wenn eine H\-Datei vorhanden ist.  
  
## Beispiel  
 Der folgende Code:  
  
```  
// cpp_attr_ref_import.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[import(import.idl)];  
```  
  
 erzeugt den folgenden Code in der generierten IDL\-Datei:  
  
```  
import "docobj.idl";  
import "import.idl";  
  
[ uuid(EED3644C-8488-3ECD-BA97-147DB3CDB499), version(1.0) ]  
library MyLib {  
   importlib("stdole2.tlb");  
   importlib("olepro32.dll");  
...  
```  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|Überall|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [importidl](../windows/importidl.md)   
 [importlib](../windows/importlib.md)   
 [include](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)