---
title: "IRowsetUpdateImpl-Klasse"
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
  - "IRowsetUpdateImpl"
  - "ATL.IRowsetUpdateImpl"
  - "ATL::IRowsetUpdateImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetUpdateImpl-Klasse"
  - "Anbieter, Aktualisierbar"
  - "Aktualisierbare Anbieter, Zurückgestelltes Update"
ms.assetid: f85af76b-ab6f-4f8b-8f4a-337c9679d68f
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetUpdateImpl-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die OLE DB\-Vorlagen\-Implementierung der [IRowsetUpdate](https://msdn.microsoft.com/en-us/library/ms714401.aspx)\-Schnittstelle.  
  
## Syntax  
  
```  
template <  
   class T,   
   class Storage,   
   class UpdateArray = CAtlArray<Storage>,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>   
>  
class IRowsetUpdateImpl : public IRowsetChangeImpl<  
   T,   
   Storage,   
   IRowsetUpdate,   
   RowClass,   
   MapClass  
>  
```  
  
#### Parameter  
 `T`  
 Eine Klasse wird von `IRowsetUpdateImpl` abgeleitet.  
  
 `Storage`  
 Der Benutzerdatensatz.  
  
 `UpdateArray`  
 Ein Array, das zwischengespeicherte Daten für das Aktualisieren des Rowsets enthält.  
  
 `RowClass`  
 Die Speichereinheit für **HROW**.  
  
 `MapClass`  
 Die Speichereinheit für alle Zeilenhandles hielt vom Anbieter an.  
  
## Member  
  
### Schnittstellenmethoden \(mit IRowsetChange\)  
  
|||  
|-|-|  
|[SetData](../../data/oledb/irowsetupdateimpl-setdata.md)|Legt Datenwerte in einer oder mehreren Spalten fest.|  
  
### Schnittstellenmethoden \(mit IRowsetUpdate\)  
  
|||  
|-|-|  
|[GetOriginalData](../../data/oledb/irowsetupdateimpl-getoriginaldata.md)|Ruft die Daten ab, die zuletzt zu übertragen werden oder von der Datenquelle abgerufen wurden und ignoriert ausstehende Änderungen.|  
|[GetPendingRows](../../data/oledb/irowsetupdateimpl-getpendingrows.md)|Gibt eine Liste der Zeilen mit ausstehenden Änderungen zurück.|  
|[GetRowStatus](../../data/oledb/irowsetupdateimpl-getrowstatus.md)|Gibt den Status der angegebenen Zeilen zurück.|  
|[Rückgängigmachen](../../data/oledb/irowsetupdateimpl-undo.md)|Führt alle Änderungen an der Zeile seit dem letzten Sammeln oder das Update rückgängig.|  
|[Aktualisieren](../../data/oledb/irowsetupdateimpl-update.md)|Sendet Änderungen, die an der Zeile seit dem letzten Sammeln oder die Aktualisierung vorgenommen werden.|  
  
### Implementierungsverfahren Rückruf\(\)  
  
|||  
|-|-|  
|[IsUpdateAllowed](../../data/oledb/irowsetupdateimpl-isupdateallowed.md)|Wird verwendet, um für Sicherheit, Integrität zu überprüfen, z. B, bevor Updates ermöglicht werden.|  
  
### Datenmember  
  
|||  
|-|-|  
|[m\_mapCachedData](../../data/oledb/irowsetupdateimpl-m-mapcacheddata.md)|Enthält die ursprünglichen Daten für den verzögerten Vorgang.|  
  
## Hinweise  
 Sie können Dokumentation [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) vertraut machen und verstehen, dass alles, das in dem Thema beschrieben wird auch, hier gilt.  Sie sollten auch Chapter 6 `OLE``DB``Programmer's``Reference` \) darüber informieren auf Einstellungsdaten.  
  
 `IRowsetUpdateImpl` implementiert die OLE DB\- `IRowsetUpdate`\-Schnittstelle, die Consumern, die Übertragung von verzögerter Aktualisierungen aktiviert, die mit `IRowsetChange` in der Datenquelle und Änderungen vor Übertragung rückgängig machen vorgenommen werden.  
  
> [!IMPORTANT]
>  VOR Sie versuchen, es wird dringend empfohlen, die der folgenden Dokumentation, den Anbieter zu implementieren lesen:  
  
-   [Erstellen für einen aktualisierbaren Anbieter](../../data/oledb/creating-an-updatable-provider.md)  
  
-   Kapitel 6 `OLE``DB``Programmer's``Reference`  
  
-   Siehe auch, wie die `RUpdateRowset`\-Klasse im UpdatePV\-Beispiel verwendet wird  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Erstellen eines aktualisierbaren Anbieters](../../data/oledb/creating-an-updatable-provider.md)