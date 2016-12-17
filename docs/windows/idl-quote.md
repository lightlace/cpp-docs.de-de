---
title: "idl_quote"
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
  - "vc-attr.idl_quote"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "idl_quote attribute"
ms.assetid: a370e1b7-948b-4e67-9a25-58facf24e4c9
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# idl_quote
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ermöglicht es Ihnen, IDL\-Konstrukte zu verwenden, die nicht in die aktuelle Version von Visual C\+\+ unterstützt werden und sie zur generierten IDL\-Datei übergeben wird.  
  
## Syntax  
  
```  
  
      [ idl_quote(  
   text  
) ]  
```  
  
#### Parameter  
 *text*  
 Der Attributname, dass Sie den Visual C\+\+\-Compiler beabsichtigen, um zur generierten IDL\-Datei von übergeben werden sollen, ohne einen Compilerfehler zurückzugeben.  
  
## Hinweise  
 Wenn das Attribut **idl\_quote** C\+\+ als eigenständiges Attribut mit einem Semikolon \(nach der eckige Klammer\) verwendet wird, wird *Text* in die zusammengeführte IDL\-Datei abgelegt.  Wenn **idl\_quote** auf ein Symbol verwendet wird, wird *Text* innerhalb eines Attributblocks für dieses Symbol platziert.  
  
## Beispiel  
 Der folgende Code zeigt, wie Sie ein Attribut angeben konnten nicht unterstützt \(mithilfe **in**, das unterstützt wird\) und wie ein nicht definiertes .idl\-Konstrukt definiert und verwendet werden:  
  
```  
// cpp_attr_ref_idl_quote.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLibrary")];  
  
[export]  
struct MYFLOT {  
   int i;  
};  
  
[export]  
struct MYDUB {  
   int i;  
};  
  
[idl_quote("typedef union _S1_TYPE switch (long l1) U1_TYPE { case 1024: \  
struct MYFLOT f1; case 2048: struct MYDUB d2; } S1_TYPE;") ];  
  
typedef struct _S1_TYPE {   
   long l1;   
  
union {   
   MYFLOT f1; MYDUB d2; } U1_TYPE;   
} S1_TYPE;  
  
[uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA"), object]  
__interface IStatic{  
   HRESULT Func1([idl_quote("in")] int i);  
   HRESULT func( S1_TYPE* myStruct );  
};  
```  
  
 Dieser Code führt MYFLOT und MYDUB und die in der generierten IDL\-Datei abgelegt werden, Texterfassung.  Der *Namensparameter* zwingt den *Text* platziert werden soll *,* bevor alle *Namen* , die in der generierten IDL\-Datei verweist.  Der Parameter erzwingt die *Abhängigkeiten* vor *Text* in der generierten IDL\-Datei abgelegt werden soll listendefinitionen Abhängigkeiten.  
  
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
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)