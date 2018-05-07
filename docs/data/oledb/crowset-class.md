---
title: CRowset-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CRowset<TAccessor>
- CRowset
- ATL::CRowset
- ATL::CRowset<TAccessor>
- ATL.CRowset
dev_langs:
- C++
helpviewer_keywords:
- CRowset class
ms.assetid: b0228a90-b8dd-47cc-b397-8d4c15c1e7f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5c9a23c2e879f0d2fe1add1a970c64f6fbcc27b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="crowset-class"></a>CRowset-Klasse
Kapselt eine OLE DB-Rowset-Objekte sowie einige weitere im Zusammenhang-Hostingschnittstellen und bietet Methoden für Rowsetdaten bearbeiten.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class TAccessor = CAccessorBase>  
class CRowset  
```  
  
#### <a name="parameters"></a>Parameter  
 `TAccessor`  
 Ein Accessorklasse. Die Standardeinstellung ist `CAccessorBase`.  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/crowset-addrefrows.md)|Inkrementiert den Verweiszähler dieser Planergruppe, die der aktuellen Zeile zugeordnet ist.|  
|[Schließen](../../data/oledb/crowset-close.md)|Zeilen und die aktuelle frei `IRowset` Schnittstelle.|  
|[Compare](../../data/oledb/crowset-compare.md)|Vergleicht zwei Lesezeichen mit [IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx).|  
|[CRowset](../../data/oledb/crowset-crowset.md)|Erstellt ein neues `CRowset` Objekt, und ordnet sie (optional) eine **IRowset** Schnittstelle als Parameter angegeben.|  
|[Löschen](../../data/oledb/crowset-delete.md)|Löscht Zeilen aus dem Rowset mit [IRowsetChange:DeleteRows](https://msdn.microsoft.com/en-us/library/ms724362.aspx).|  
|[FindNextRow](../../data/oledb/crowset-findnextrow.md)|Sucht das nächste übereinstimmende Zeile nach dem angegebenen Lesezeichen.|  
|[GetApproximatePosition](../../data/oledb/crowset-getapproximateposition.md)|Gibt die ungefähre Position einer Zeile zu einem Lesezeichen entspricht.|  
|[GetData](../../data/oledb/crowset-getdata.md)|Ruft Daten aus dem Rowset Kopie der Zeile ab.|  
|[GetDataHere](../../data/oledb/crowset-getdatahere.md)|Ruft Daten aus dem angegebenen Puffer ab.|  
|[GetOriginalData](../../data/oledb/crowset-getoriginaldata.md)|Ruft die Daten zuletzt aus dem Verbindungspool abgerufen oder an der Datenquelle wird ignoriert, wenn ausstehende Änderungen übertragen.|  
|[GetRowStatus](../../data/oledb/crowset-getrowstatus.md)|Gibt den Status aller Zeilen zurück.|  
|[Einfügen](../../data/oledb/crowset-insert.md)|Erstellt und fügt eine neue Zeile mit [IRowsetChange:InsertRow](https://msdn.microsoft.com/en-us/library/ms716921.aspx).|  
|[IsSameRow](../../data/oledb/crowset-issamerow.md)|Vergleicht die angegebene Zeile mit der aktuellen Zeile.|  
|[MoveFirst](../../data/oledb/crowset-movefirst.md)|Positioniert den weiter-Fetch-Speicherort an der Anfangsposition.|  
|[MoveLast](../../data/oledb/crowset-movelast.md)|Wechselt zum letzten Datensatz.|  
|[MoveNext](../../data/oledb/crowset-movenext.md)|Ruft Daten aus der nächsten sequenziellen Zeile oder eine angegebene Anzahl von Positionen hinter die nächste Zeile ab.|  
|[MovePrev](../../data/oledb/crowset-moveprev.md)|Wechselt zum vorherigen Datensatzes.|  
|[MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)|Ruft die von einer Textmarke markierte Zeile oder die Zeile an einem angegebenen Offset aus diesem Lesezeichen ab.|  
|[MoveToRatio](../../data/oledb/crowset-movetoratio.md)|Ruft Zeilen ab der ein Bruchteilen Position im Rowset ab.|  
|[ReleaseRows](../../data/oledb/crowset-releaserows.md)|Aufrufe [IRowset:: ReleaseRows](https://msdn.microsoft.com/en-us/library/ms719771.aspx) in der aktuellen Zeilenhandle freigegeben.|  
|[SetData](../../data/oledb/crowset-setdata.md)|Legt Datenwerte in einer oder mehreren Spalten einer Zeile mit [IRowsetChange:SetData](https://msdn.microsoft.com/en-us/library/ms721232.aspx).|  
|[rückgängig machen](../../data/oledb/crowset-undo.md)|Macht alle Änderungen an einer Zeile seit der letzten Fetch oder [Update](../../data/oledb/crowset-update.md).|  
|[Update (Aktualisieren)](../../data/oledb/crowset-update.md)|Überträgt alle ausstehenden Änderungen an der aktuellen Zeile seit der letzten Fetch oder Update.|  
|[UpdateAll](../../data/oledb/crowset-updateall.md)|Überträgt alle ausstehenden Änderungen, die seit der letzten Fetch oder Aktualisierung auf alle Zeilen.|  
  
## <a name="remarks"></a>Hinweise  
 In der OLE DB ist ein Rowset für das Objekt, durch das ein Programm, legt sie fest, und ruft Daten ab.  
  
 Diese Klasse ist nicht vorgesehen, instanziiert werden, sondern stattdessen als einen Vorlagenparameter übergeben `CTable` oder `CCommand` (`CRowset` ist die Standardeinstellung).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [DBViewer-Beispiel](../../visual-cpp-samples.md)   
 [MultiRead-Beispiel](../../visual-cpp-samples.md)   
 [Beispiel für MultiRead-Attribute](../../visual-cpp-samples.md)   
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)