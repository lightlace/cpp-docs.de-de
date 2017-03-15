---
title: "CDynamicAccessor::GetColumnInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetColumnInfo"
  - "ATL.CDynamicAccessor.GetColumnInfo"
  - "ATL::CDynamicAccessor::GetColumnInfo"
  - "CDynamicAccessor.GetColumnInfo"
  - "CDynamicAccessor::GetColumnInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetColumnInfo-Methode"
ms.assetid: 7f2102ea-b7cc-4714-812f-3ca2857f4b9a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::GetColumnInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt die von den meisten Consumern benötigten Spaltenmetadaten zurück.  
  
## Syntax  
  
```  
  
      HRESULT GetColumnInfo(   
   IRowset* pRowset,   
   DBORDINAL* pColumns,   
   DBCOLUMNINFO** ppColumnInfo,   
   OLECHAR** ppStringsBuffer    
) throw( );  
```  
  
#### Parameter  
 `pRowset`  
 \[in\] Ein Zeiger zur [IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx)\-Schnittstelle.  
  
 *pColumns*  
 \[out\] Ein Zeiger im dem Arbeitsspeicher, um die Anzahl der Spalten im Rowset zurückgibt; Diese Zahl schließt die Lesezeichenspalte, sofern vorhanden.  
  
 *ppColumnInfo*  
 \[out\] Ein Zeiger auf den Speicher, in dem einem Array von **DBCOLUMNINFO**, zurückzugeben strukturiert.  Siehe, dass "DBCOLUMNINFO" in [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) in der *OLE* DB\-Programmierreferenz strukturiert.  
  
 `ppStringsBuffer`  
 \[out\] Ein Zeiger in dem im Speicher, einen Zeiger auf den Speicher aller Zeichenfolgenwerte \(Namen haben entweder innerhalb *des columnid* oder für *pwszName*\), innerhalb eines einzelnen Zuordnungsblocks zurückzugeben.  
  
## Rückgabewert  
 Einer der Standard\- `HRESULT`\-Werte.  
  
## Hinweise  
 Siehe [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) in *der OLE DB\-Programmierreferenz* Informationen zu Datentypen die **DBORDINAL**, **DBCOLUMNINFO** und **OLECHAR**.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDynamicAccessor\-Klasse](../../data/oledb/cdynamicaccessor-class.md)