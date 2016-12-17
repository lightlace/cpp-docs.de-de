---
title: "com::ptr"
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
  - "ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "com::ptr"
ms.assetid: ee302e3c-8fed-4875-a372-2e55003718d3
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# com::ptr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Wrapper für ein COM\-Objekt, die als Member einer CLR\-Klasse verwendet werden kann.  Der Wrapper automatisiert zudem die Lebensdauerverwaltung des COM\-Objekts und gibt besessene Verweise auf das Objekt frei, wenn ihr Destruktor aufgerufen wird.  Analog [CComPtr Class](../atl/reference/ccomptr-class.md).  
  
## Syntax  
  
```  
#include <msclr\com\ptr.h>  
```  
  
## Hinweise  
 [com::ptr\-Klasse](../dotnet/com-ptr-class.md) ist in der Datei \<msclr\\com\\ptr.h\> definiert.  
  
## Siehe auch  
 [C\+\+\-Unterstützungsbibliothek](../dotnet/cpp-support-library.md)