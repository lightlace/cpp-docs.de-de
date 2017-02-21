---
title: "CDaoIndexFieldInfo-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDaoIndexFieldInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoIndexFieldInfo-Struktur"
  - "DAO (Datenzugriffsobjekte), Indexfelderauflistung"
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# CDaoIndexFieldInfo-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CDaoIndexFieldInfo`\-Struktur enthält Informationen über ein Indexfeldobjekt, das für Datenzugriffsobjekte \(DAO\) definiert ist.  
  
## Syntax  
  
```  
  
      struct CDaoIndexFieldInfo  
{  
   CString m_strName;          // Primary  
   BOOL m_bDescending;         // Primary  
};  
```  
  
#### Parameter  
 `m_strName`  
 Benennt das eindeutig Indexfeldobjekt.  Ausführliche Informationen finden Sie im Thema "Name\-Eigenschaft" in der DAO\-Hilfe.  
  
 *M\_bDescending*  
 Gibt der Indexreihenfolge an, die vom Indexobjekt definiert wird.  **TRUE**, wenn die Reihenfolge absteigend ist.  
  
## Hinweise  
 Ein Indexobjekt kann einige Felder verfügen und angeben, das eine tabledef\- \(oder ein Recordset auf einer Tabelle basiert\) ist indiziert an Felder.  Die Verweise auf primärem oben genanntem geben an, wie diese Informationen im `m_pFieldInfos`\-Member eines [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md)\-Objekts zurückgegeben werden, das mithilfe der `GetIndexInfo`\-Memberfunktion der [CDaoTableDef](../Topic/CDaoTableDef::GetIndexInfo.md) oder [CDaoRecordset](../Topic/CDaoRecordset::GetIndexInfo.md) abgerufen wird, aufgerufen.  
  
 Indexobjekte und Indexfeldobjekte werden nicht durch eine MFC\-Klasse dargestellt.  Stattdessen enthält die DAO\-Objekte MFC\-Objekten, die der [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) zugrunde liegen, eine Auflistung Indexobjekte, die aufgerufen Indexauflistung.  Jedes Indexobjekt enthält wiederum eine Auflistung Feldobjekte.  Diese Klassen stellen Memberfunktionen, um auf einzelne Elemente aus Indexinformationen zuzugreifen, oder Sie können mit einem `CDaoIndexInfo`\-Objekt in einem gemeinsam zugreifen, indem Sie die Memberfunktion `GetIndexInfo` des enthaltenden Objekts aufrufen.  Das `CDaoIndexInfo`\-Objekt hat und dann ein Datenmember, `m_pFieldInfos`, der in einem Array `CDaoIndexFieldInfo`\-Objekten zeigt.  
  
 Rufen Sie die Memberfunktion `GetIndexInfo` der enthaltenden tabledef\- oder des Recordset\-Objekts auf, in dessen Indizes Auflistung das Indexobjekt gespeichert wird, das, Sie interessiert.  Informieren Sie dann das `m_pFieldInfos`[CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md)\-Member des Objekts.  Die Länge des Arrays `m_pFieldInfos` wird in `m_nFields` gespeichert.  `CDaoIndexFieldInfo` definiert auch eine `Dump`\-Memberfunktion in Debugbuilds.  Sie können `Dump` verwenden, um den Inhalt eines `CDaoIndexFieldInfo`\-Objekts zu speichern.  
  
## Anforderungen  
 **Header:** afxdao.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../Topic/CDaoTableDef::GetIndexInfo.md)   
 [CDaoRecordset::GetIndexInfo](../Topic/CDaoRecordset::GetIndexInfo.md)