---
title: "uuid (C++ Attributes)"
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
  - "vc-attr.uuid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "uuid attribute"
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# uuid (C++ Attributes)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt die eindeutige ID für eine Klasse oder eine Schnittstelle an.  
  
## Syntax  
  
```  
  
      [ uuid(  
   "uuid"  
) ]  
```  
  
#### Parameter  
 *uuid*  
 Ein eindeutiger Bezeichner, 128\-Bit.  
  
## Hinweise  
 Wenn die Definition einer Klasse oder Schnittstelle das Attribut nicht `uuid` C\+\+ angibt, dann stellt der Visual C\+\+\-Compiler ein.  Wenn Sie `uuid`angeben, müssen Sie die Anführungszeichen einschließen.  
  
 Wenn Sie nicht `uuid`angeben, generiert der Compiler das gleiche GUID für Klassen oder Schnittstellen mit demselben Namen in verschiedenen Attribut projekten auf einem Computer.  
  
 Sie können Uuidgen.exe oder Guidgen.exe verwenden, um zu generieren, eindeutige ID besitzen.  \(Irgendeinen dieser Tools, und klicken Sie **Start** klicken Sie im Menü **Ausführen** ausführen.  Geben Sie dann den Namen des erforderlichen Tools ein.\)  
  
 Wenn in einem Projekt verwendet wird, die nicht außerdem ATL verwendet, das `uuid`\-Attribut ist dasselbe wie anzugeben, den [uuid](../cpp/uuid-cpp.md) declspec\-Modifizierer angibt.  Um `uuid` einer Klasse abzurufen, können Sie mithilfe [\_\_uuidof](../cpp/uuidof-operator.md)  
  
## Beispiel  
 Weitere Informationen finden Sie im [bindbar](../windows/bindable.md) Beispiel für eine Beispiel verwenden aus `uuid`.  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`, `interface`, **Union**, `enum`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [uuid](http://msdn.microsoft.com/library/windows/desktop/aa367302)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)