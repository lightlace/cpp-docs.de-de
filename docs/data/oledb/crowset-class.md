---
title: "CRowset-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CRowset<TAccessor>"
  - "CRowset"
  - "ATL::CRowset"
  - "ATL::CRowset<TAccessor>"
  - "ATL.CRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRowset-Klasse"
ms.assetid: b0228a90-b8dd-47cc-b397-8d4c15c1e7f4
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# CRowset-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt ein OLE DB\-Rowsetobjekt und verschiedene verwandte Schnittstellen und stellt Manipulationsmethoden für Rowsetdaten bereit.  
  
## Syntax  
  
```  
template <class TAccessor = CAccessorBase>  
class CRowset  
```  
  
#### Parameter  
 `TAccessor`  
 Eine Accessorklasse.  Die Standardeinstellung ist `CAccessorBase`.  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/crowset-addrefrows.md)|Inkrementiert den Verweiszähler, der der aktuellen Zeile zugeordnet ist.|  
|[Schließen](../../data/oledb/crowset-close.md)|Versionszeilen und die aktuelle `IRowset`\-Schnittstelle.|  
|[Compare](../../data/oledb/crowset-compare.md)|Vergleicht zwei Lesezeichen mit [IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx).|  
|[CRowset](../../data/oledb/crowset-crowset.md)|Erstellt ein neues `CRowset`\-Objekt und \(optional\) weist dieses mit einer **IRowset** \-Schnittstelle zu, die als Parameter angegeben wird.|  
|[Löschen](../../data/oledb/crowset-delete.md)|Zeilen löschen aus dem Rowset mit [IRowsetChange: DeleteRows](https://msdn.microsoft.com/en-us/library/ms724362.aspx).|  
|[FindNextRow](../../data/oledb/crowset-findnextrow.md)|Sucht die nächste entsprechende Zeile nach das angegebene Lesezeichen.|  
|[GetApproximatePosition](../../data/oledb/crowset-getapproximateposition.md)|Gibt die ungefähre Position eine Zeile entsprechend einem Lesezeichen zurück.|  
|[GetData](../../data/oledb/crowset-getdata.md)|Ruft Daten von der Zeilenkopie des Rowsets ab.|  
|[GetDataHere](../../data/oledb/crowset-getdatahere.md)|Ruft Daten im angegebenen Puffer ab.|  
|[GetOriginalData](../../data/oledb/crowset-getoriginaldata.md)|Ruft die Daten ab, die zuletzt von abgerufen werden oder die Datenquelle gesendet sind und ignoriert ausstehende Änderungen.|  
|[GetRowStatus](../../data/oledb/crowset-getrowstatus.md)|Gibt den Status aller Zeilen zurück.|  
|[Insert](../../data/oledb/crowset-insert.md)|Erstellt und fügt eine neue Zeile mit [IRowsetChange: InsertRow](https://msdn.microsoft.com/en-us/library/ms716921.aspx).|  
|[IsSameRow](../../data/oledb/crowset-issamerow.md)|Vergleicht die angegebene Zeile mit der aktuellen Zeile.|  
|[MoveFirst](../../data/oledb/crowset-movefirst.md)|Ordnet den NEXTAbrufspeicherort zur Anfangsposition neu.|  
|[MoveLast](../../data/oledb/crowset-movelast.md)|Wechselt zum letzten Datensatz.|  
|[MoveNext](../../data/oledb/crowset-movenext.md)|abgerufen von sequenziellen der folgenden Zeile oder eine angegebene Anzahl Positionen zu der folgenden Zeile hinaus.|  
|[MovePrev](../../data/oledb/crowset-moveprev.md)|Wechselt zum vorherigen Datensatz.|  
|[MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)|Ruft die Zeile ab, die von ein Lesezeichen gekennzeichnet oder die Zeile an einem angegebenen Offset von diesem Lesezeichen.|  
|[MoveToRatio](../../data/oledb/crowset-movetoratio.md)|Ruft den Start\- Zeilen aus einer Bruchposition im Rowset.|  
|[ReleaseRows](../../data/oledb/crowset-releaserows.md)|Ruft [IRowset::ReleaseRows](https://msdn.microsoft.com/en-us/library/ms719771.aspx) auf, um das aktuelle Zeilenhandle freizugeben.|  
|[SetData](../../data/oledb/crowset-setdata.md)|Legt Datenwerte in einer oder mehreren Spalten einer Zeile mit [IRowsetChange: SetData](https://msdn.microsoft.com/en-us/library/ms721232.aspx) fest.|  
|[Rückgängigmachen](../../data/oledb/crowset-undo.md)|Führt alle Änderungen rückgängig an einer Zeile seit dem letzten Sammeln oder [Aktualisieren](../../data/oledb/crowset-update.md) vorgenommen werden.|  
|[Aktualisieren](../../data/oledb/crowset-update.md)|Sendet alle ausstehenden Änderungen, die der aktuellen Zeile seit dem letzten Sammeln oder die Aktualisierung vorgenommen werden.|  
|[UpdateAll](../../data/oledb/crowset-updateall.md)|Sendet alle ausstehenden Änderungen, die an allen Zeilen seit dem letzten Sammeln oder die Aktualisierung vorgenommen werden.|  
  
## Hinweise  
 In OLE DB ist ein Rowset das Objekt, durch das ein Programm Daten festgelegt und abgerufen wird.  
  
 Diese Klasse ist nicht vorgesehen instanziiert werden jedoch als einen Vorlagenparameter an `CTable` oder `CCommand` \(`CRowset` ist der Standardwert\) nicht übergeben werden.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [DBViewer\-Beispiel](../../top/visual-cpp-samples.md)   
 [MultiRead\-Beispiel](../../top/visual-cpp-samples.md)   
 [Beispiel für MultiRead\-Attribute](../../top/visual-cpp-samples.md)   
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)