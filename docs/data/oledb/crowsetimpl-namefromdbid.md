---
title: "CRowsetImpl::NameFromDBID"
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
  - "CRowsetImpl.NameFromDBID"
  - "CRowsetImpl::NameFromDBID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NameFromDBID-Methode"
ms.assetid: 6aa5b074-90c7-4434-adfd-c64c13e76c78
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CRowsetImpl::NameFromDBID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Extrahiert eine Zeichenfolge von **DBID** und kopiert sie auf `bstr`, das übergeben wird.  
  
## Syntax  
  
```  
  
      HRESULT CRowsetBaseImpl::NameFromDBID(  
   DBID* pDBID,  
   CComBSTR& bstr,  
   bool bIndex   
);  
```  
  
#### Parameter  
 *pDBID*  
 \[in\] Ein Zeiger auf von denen **DBID**, um eine Zeichenfolge zu extrahieren.  
  
 `bstr`  
 \[in\] Verweis A der [CComBSTR](../../atl/reference/ccombstr-class.md), um eine Kopie der Zeichenfolge **DBID** zu platzieren.  
  
 `bIndex`  
 \[in\] **true** wenn ein Index **DBID**; **false** Wenn eine Tabelle **DBID**.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  Je nachdem, ob **DBID** eine Tabelle ist, oder einem Index \(dargestellt durch `bIndex`\), gibt die Methode **DB\_E\_NOINDEX** oder **DB\_E\_NOTABLE** zurück.  
  
## Hinweise  
 Diese Methode wird von der `CRowsetImpl` Implementierungen von [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) und [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md) aufgerufen.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [CRowsetImpl\-Klasse](../../data/oledb/crowsetimpl-class.md)