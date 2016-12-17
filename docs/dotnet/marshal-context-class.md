---
title: "marshal_context-Klasse"
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
  - "marshal_context"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "marshal_context-Klasse [C++]"
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# marshal_context-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Klasse konvertiert Daten zwischen systemeigenen und verwalteten Umgebungen.  
  
## Syntax  
  
```  
class marshal_context  
```  
  
## Hinweise  
 Verwenden Sie die `marshal_context`\-Klasse für Datenkonvertierungen, die einen Kontext erfordert.  Weitere Informationen finden Sie unter [Übersicht über das Marshaling in C\+\+](../dotnet/overview-of-marshaling-in-cpp.md), über Konvertierungen einen Kontext benötigen und die Marshallingdatei enthalten sein muss.  Das Ergebnis des Marshallens, wenn Sie einen Kontext verwenden, ist nur gültig, bis das `marshal_context`\-Objekt zerstört wird.  Um das Ergebnis beizubehalten, müssen Sie die Daten kopieren.  
  
 Gleiche `marshal_context` kann für mehrere Datenkonvertierungen verwendet werden.  Die Wiederverwendung des Kontexts auf diese Weise hat nicht die Ergebnisse aus den vorherigen Marshallingsaufrufen.  
  
## Anforderungen  
 **Headerdatei:** \<msclr\\marshal.h\>, \<msclr\\marshal\_windows.h\>, \<msclr\\marshal\_cppstd.h\> oder \<msclr\\marshal\_atl.h\>  
  
 **Namespace:** msclr::interop  
  
## Siehe auch  
 [Übersicht über das Marshaling in C\+\+](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal\_as](../dotnet/marshal-as.md)