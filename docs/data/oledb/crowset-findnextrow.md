---
title: "CRowset::FindNextRow"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "ATL.CRowset.FindNextRow"
  - "CRowset<TAccessor>.FindNextRow"
  - "ATL::CRowset::FindNextRow"
  - "CRowset::FindNextRow"
  - "CRowset<TAccessor>::FindNextRow"
  - "CRowset.FindNextRow"
  - "ATL.CRowset<TAccessor>.FindNextRow"
  - "ATL::CRowset<TAccessor>::FindNextRow"
  - "FindNextRow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FindNextRow-Methode"
ms.assetid: 36484df9-3625-4f15-bf69-db73a8d91c55
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::FindNextRow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sucht die nächste entsprechende Zeile nach das angegebene Lesezeichen.  
  
## Syntax  
  
```  
  
      HRESULT FindNextRow(   
   DBCOMPAREOP op,   
   BYTE* pData,   
   DBTYPE wType,   
   DBLENGTH nLength,   
   BYTE bPrecision,   
   BYTE bScale,   
   BOOL bSkipCurrent = TRUE,   
   CBookmarkBase* pBookmark = NULL    
) throw( );  
```  
  
#### Parameter  
 `op`  
 \[in\] der wenn zu verwenden, Vorgang, Zeilenwerte verglichen werden.  Für Werte finden Sie unter [IRowsetFind::FindNextRow](https://msdn.microsoft.com/en-us/library/ms723091.aspx).  
  
 `pData`  
 \[in\] Ein Zeiger auf den Wert verglichen werden.  
  
 `wType`  
 \[in\] gibt den Datentyp des Wertteils des Puffers an.  Informationen zum Typindikatoren, finden Sie unter [Datentypen](https://msdn.microsoft.com/en-us/library/ms723969.aspx) in der *OLE* DB\-Programmierreferenz in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `nLength`  
 \[in\] die Länge, in Bytes, der Consumerdatenstruktur zugeordnet für den zu untersuchenden Datenwert aus.  Weitere Informationen finden Sie in der Beschreibung von **cbMaxLen** in [DBBINDING\-Strukturen](https://msdn.microsoft.com/en-us/library/ms716845.aspx) in der *OLE DB\-Programmierreferenz.*  
  
 `bPrecision`  
 \[in\] Die maximale Genauigkeit verwendet werden, wenn Daten abgerufen werden.  Wird nur, wenn `wType``DBTYPE_NUMERIC` ist.  Weitere Informationen finden Sie unter [Konvertierungen, die DBTYPE\_NUMERIC oder DBTYPE\_DECIMAL beinhalten](https://msdn.microsoft.com/en-us/library/ms719714.aspx) in der *OLE* DB\-Programmierreferenz.  
  
 `bScale`  
 \[in\] die Dezimalstellen verwendet werden, wenn Daten abgerufen werden.  Wird nur, wenn `wType``DBTYPE_NUMERIC` oder **DBTYPE\_DECIMAL** aufweist.  Weitere Informationen finden Sie unter [Konvertierungen, die DBTYPE\_NUMERIC oder DBTYPE\_DECIMAL beinhalten](https://msdn.microsoft.com/en-us/library/ms719714.aspx) in der *OLE* DB\-Programmierreferenz.  
  
 *bSkipCurrent*  
 \[in\] Die Anzahl von Zeilen an den vom Lesezeichen, eine Suche zu beginnen.  
  
 `pBookmark`  
 \[in\] Das Lesezeichen für an der Position, eine Suche zu beginnen.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Diese Methode erfordert die optionale Schnittstelle **IRowsetFind**, die möglicherweise nicht auf alle Anbieter unterstützt wird; Wenn dies der Fall ist, gibt die Methode **E\_NOINTERFACE** zurück.  Sie müssen **DBPROP\_IRowsetFind** auf `VARIANT_TRUE` festlegen, bevor Sie auf dem Tisch **Öffnen** aufrufen oder den Befehl, das Rowset enthalten.  
  
 Informationen zur Verwendung kennzeichnet in Consumern, finden Sie unter [Verwenden von Lesezeichen](../../data/oledb/using-bookmarks.md).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CRowset\-Klasse](../../data/oledb/crowset-class.md)   
 [DBBINDING Structures](https://msdn.microsoft.com/en-us/library/ms716845.aspx)