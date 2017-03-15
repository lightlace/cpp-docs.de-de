---
title: "ICommandTextImpl-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ICommandText"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICommandText-Klasse"
ms.assetid: 9c2715cc-1e55-4468-8327-85341617ed46
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# ICommandTextImpl-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Implementierung für die [ICommandText](https://msdn.microsoft.com/en-us/library/ms714914.aspx)\-Schnittstelle bereit.  
  
## Syntax  
  
```  
template <class T >  
class ATL_NO_VTABLE ICommandTextImpl   
   : public ICommandImpl<T, ICommandText>  
```  
  
#### Parameter  
 `T`  
 Die Befehlsklasse von **ICommandTextImpl** abgeleitet.  
  
## Member  
  
### Schnittstellenmethoden  
  
|||  
|-|-|  
|[GetCommandText](../../data/oledb/icommandtextimpl-getcommandtext.md)|Gibt den Textbefehlssatz vom letzten Aufruf der [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md) zurück.|  
|[SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md)|Legt den Befehlstext fest und ersetzt vorhandenen Befehlstext.|  
  
### Datenmember  
  
|||  
|-|-|  
|[m\_strCommandText](../../data/oledb/icommandtextimpl-m-strcommandtext.md)|Speichert den Befehlstext.|  
  
## Hinweise  
 Eine erforderliche Schnittstelle auf Befehlen.  
  
## Anforderungen  
 **Header:**  altdb.h  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)