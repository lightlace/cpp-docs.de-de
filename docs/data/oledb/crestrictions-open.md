---
title: "CRestrictions::Open"
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
  - "CRestrictions.Open"
  - "ATL::CRestrictions::Open"
  - "ATL.CRestrictions.Open"
  - "CRestrictions::Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open-Methode"
ms.assetid: 0aff0cc3-543a-47d2-8d6b-ebb36926b6db
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CRestrictions::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt ein Resultset entsprechend den vom Benutzer bereitgestellten Einschränkungen zurück.  
  
## Syntax  
  
```  
  
      HRESULT Open(  
   const CSession& session,  
   LPCTSTR lpszParam 1 = NULL,  
   LPCTSTR lpszParam 2 = NULL,  
   LPCTSTR lpszParam 3 = NULL,  
   LPCTSTR lpszParam 4 = NULL,  
   LPCTSTR lpszParam 5 = NULL,  
   LPCTSTR lpszParam 6 = NULL,  
   LPCTSTR lpszParam 7 = NULL,  
   bool bBind = true  
);  
```  
  
#### Parameter  
 `session`  
 \[in\] gibt einem vorhandenen Sitzungsobjekt fest, das verwendet wird, um die Datenquelle herzustellen.  
  
 *lpszParam*  
 \[in\] gibt den Einschränkungen im Schemarowset an.  
  
 `bBind`  
 \[in\] gibt an, ob die Spaltenzuordnung automatisch gebunden wird.  Der Standardwert ist **true**, der die Spaltenzuordnung wird, automatisch gebunden werden.  Einstellung `bBind` von **false** verhindert die automatische Bindung der Spaltenzuordnung, damit Sie manuell binden können. \(Das manuelle Bindung ist von besonderem Interesse für OLAP\-Benutzern.\)  
  
## Rückgabewert  
 Einer der Standard\- `HRESULT`\-Werte.  
  
## Hinweise  
 Sie können eine Maximal\- von sieben Beschränkungen für ein Schemarowset angeben.  
  
 Siehe [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) für Informationen über die definierten Einschränkungen auf jedem Schemarowset.  
  
## Anforderungen  
 **Header:** atldbsch.h  
  
## Siehe auch  
 [CRestrictions\-Klasse](../../data/oledb/crestrictions-class.md)   
 [Schemarowset\-Klassen und Typedef\-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)