---
title: "marshal_context::~marshal_context"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "marshal_context::~marshal_context"
  - "msclr.interop.marshal_context.~marshal_context"
  - "marshal_context.~marshal_context"
  - "msclr::interop::marshal_context::~marshal_context"
  - "~marshal_context"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "marshal_context-Klasse [C++], Operationen"
ms.assetid: 34c41b38-4c33-4f61-b74e-831ac46b4ab5
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# marshal_context::~marshal_context
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Zerstört ein `marshal_context`\-Objekt.  
  
## Syntax  
  
```  
~marshal_context();  
```  
  
## Hinweise  
 Einige Datenkonvertierungen erfordern einen Marschallkontext.  Weitere Informationen finden Sie unter [Übersicht über das Marshaling in C\+\+](../dotnet/overview-of-marshaling-in-cpp.md), welche Übersetzungen einen Kontext benötigen und die Marshallingdatei in der Anwendung enthalten sein muss.  
  
 Ein `marshal_context`\-Objekt löschen, werden die Daten ungültig durch diesen Kontext konvertiert werden.  Wenn Sie Daten beibehalten möchten, nachdem ein `marshal_context`\-Objekt zerstört wurde, müssen Sie die Daten in eine Variable manuell kopieren, die weiter besteht.  
  
## Anforderungen  
 **Headerdatei:** \<msclr\\marshal.h\>, \<msclr\\marshal\_windows.h\>, \<msclr\\marshal\_cppstd.h\> oder \<msclr\\marshal\_atl.h\>  
  
 **Namespace:** msclr::interop  
  
## Siehe auch  
 [Übersicht über das Marshaling in C\+\+](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal\_as](../dotnet/marshal-as.md)   
 [marshal\_context\-Klasse](../dotnet/marshal-context-class.md)