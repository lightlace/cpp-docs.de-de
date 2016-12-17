---
title: "CRowset::GetApproximatePosition"
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
  - "ATL::CRowset::GetApproximatePosition"
  - "ATL::CRowset<TAccessor>::GetApproximatePosition"
  - "CRowset.GetApproximatePosition"
  - "CRowset::GetApproximatePosition"
  - "GetApproximatePosition"
  - "ATL.CRowset.GetApproximatePosition"
  - "CRowset<TAccessor>::GetApproximatePosition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetApproximatePosition-Methode"
ms.assetid: 8f9ccd41-0590-468e-b202-6731d0f99d21
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::GetApproximatePosition
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt die ungefähre Position eine Zeile entsprechend einem Lesezeichen zurück.  
  
## Syntax  
  
```  
  
      HRESULT GetApproximatePosition(   
   const CBookmarkBase* pBookmark,   
   DBCOUNTITEM* pPosition,   
   DBCOUNTITEM* pcRows    
) throw( );  
```  
  
#### Parameter  
 `pBookmark`  
 \[in\] Ein Zeiger zu einem Lesezeichen, das die Zeile identifiziert, deren Position gefunden werden soll.  **NULL**, wenn nur die Zeilenanzahl erforderlich ist.  
  
 *pPosition*  
 \[out\] Ein Zeiger zum Speicherort, in dem `GetApproximatePosition` der Position der Zeilen zurückgibt.  **NULL**, wenn die Position nicht erforderlich ist.  
  
 `pcRows`  
 \[out\] Ein Zeiger zum Speicherort, in dem `GetApproximatePosition` der Gesamtanzahl von Zeilen zurückgibt.  **NULL**, wenn die Zeilenanzahl nicht erforderlich.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Diese Methode erfordert die optionale `IRowsetScroll`\- Schnittstelle, die möglicherweise nicht auf alle Anbieter unterstützt wird; Wenn dies der Fall ist, gibt die Methode **E\_NOINTERFACE** zurück.  Sie müssen **DBPROP\_IRowsetScroll** auf `VARIANT_TRUE` festlegen, bevor Sie auf dem Tisch **Öffnen** aufrufen oder den Befehl, das Rowset enthalten.  
  
 Informationen zur Verwendung kennzeichnet in Consumern, finden Sie unter [Verwenden von Lesezeichen](../../data/oledb/using-bookmarks.md).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CRowset\-Klasse](../../data/oledb/crowset-class.md)   
 [IRowsetScroll::GetApproximatePosition](https://msdn.microsoft.com/en-us/library/ms712901.aspx)