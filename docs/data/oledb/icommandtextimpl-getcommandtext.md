---
title: "ICommandTextImpl::GetCommandText"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "GetCommandText"
  - "ICommandTextImpl.GetCommandText"
  - "ICommandTextImpl::GetCommandText"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCommandText-Methode"
ms.assetid: 0f8da470-b1c3-4573-974f-1acc111e3984
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# ICommandTextImpl::GetCommandText
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt den Textbefehlssatz vom letzten Aufruf der [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md) zurück.  
  
## Syntax  
  
```  
  
      STDMETHOD(GetCommandText)(   
   GUID * pguidDialect,   
   LPOLESTR * ppwszCommand    
);  
```  
  
#### Parameter  
 Siehe [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) in der *OLE* DB\-Programmierreferenz.  Der *pguidDialect*\-Parameter wird standardmäßig ignoriert.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [ICommandTextImpl\-Klasse](../../data/oledb/icommandtextimpl-class.md)