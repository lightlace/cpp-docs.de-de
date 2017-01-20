---
title: "marshal_context::marshal_context"
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
  - "msclr::interop::marshal_context::marshal_context"
  - "marshal_context::marshal_context"
  - "msclr.interop.marshal_context.marshal_context"
  - "marshal_context.marshal_context"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "marshal_context-Klasse [C++], Operationen"
ms.assetid: 5f08c895-60b0-4f72-97ff-7ae37c68e853
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# marshal_context::marshal_context
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt ein `marshal_context`\-Objekt zur Verwendung für Datenkonvertierung zwischen verwalteten und systemeigenen Datentypen.  
  
## Syntax  
  
```  
marshal_context();  
```  
  
## Hinweise  
 Einige Datenkonvertierungen erfordern einen Marschallkontext.  Weitere Informationen finden Sie unter [Übersicht über das Marshaling in C\+\+](../dotnet/overview-of-marshaling-in-cpp.md), welche Übersetzungen einen Kontext benötigen und die Marshallingdatei in der Anwendung enthalten sein muss.  
  
## Beispiel  
 Ein Beispiel hierfür finden Sie unter [marshal\_context::marshal\_as](../dotnet/marshal-context-marshal-as.md).  
  
## Anforderungen  
 **Headerdatei:** \<msclr\\marshal.h\>, \<msclr\\marshal\_windows.h\>, \<msclr\\marshal\_cppstd.h\> oder \<msclr\\marshal\_atl.h\>  
  
 **Namespace:** msclr::interop  
  
## Siehe auch  
 [Übersicht über das Marshaling in C\+\+](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal\_as](../dotnet/marshal-as.md)   
 [marshal\_context\-Klasse](../dotnet/marshal-context-class.md)