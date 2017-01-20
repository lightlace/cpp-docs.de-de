---
title: "IRowsetChangeImpl-Klasse"
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
  - "ATL::IRowsetChangeImpl"
  - "IRowsetChangeImpl"
  - "ATL.IRowsetChangeImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetChangeImpl-Klasse"
  - "Anbieter, Aktualisierbar"
  - "Aktualisierbare Anbieter, Direktes Update"
ms.assetid: 1e9fee15-ed9e-4387-af8f-215569beca6c
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetChangeImpl-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die OLE DB\-Vorlagen\-Implementierung der [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx)\-Schnittstelle in der OLE DB\-Spezifikation.  
  
## Syntax  
  
```  
template <  
   class T,   
   class Storage,   
   class BaseInterface = IRowsetChange,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap < RowClass::KeyType, RowClass* >   
>  
class ATL_NO_VTABLE IRowsetChangeImpl : public BaseInterface  
```  
  
#### Parameter  
 `T`  
 Eine Klasse wird von `IRowsetChangeImpl` abgeleitet.  
  
 `Storage`  
 Der Benutzerdatensatz.  
  
 `BaseInterface`  
 Die Basisklasse für die Schnittstelle, wie `IRowsetChange`.  
  
 `RowClass`  
 Die Speichereinheit für das Zeilenhandle.  
  
 `MapClass`  
 Die Speichereinheit für alle Zeilenhandles hielt vom Anbieter an.  
  
## Member  
  
### Schnittstellenmethoden \(mit IRowsetChange\)  
  
|||  
|-|-|  
|[DeleteRows](../../data/oledb/irowsetchangeimpl-deleterows.md)|Zeilen löschen aus dem Rowset.|  
|[InsertRow](../../data/oledb/irowsetchangeimpl-insertrow.md)|Fügt eine Zeile in das Rowset ein.|  
|[SetData](../../data/oledb/irowsetchangeimpl-setdata.md)|Legt Datenwerte in einer oder mehreren Spalten fest.|  
  
### Implementierungsverfahren Rückruf\(\)  
  
|||  
|-|-|  
|[FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md)|Overidden durch den Anbieter auf, um Daten in den Speicher zu übernehmen.|  
  
## Hinweise  
 Diese Schnittstelle ist für unmittelbare und Schreibvorgänge in einem Datenspeicher zuständig. "Unmittelbar" bedeutet, dass, wenn der Endbenutzer \(die Person, die Consumern verwendet\) Änderungen vornimmt, diese Änderungen sofort am Datenspeicher übertragen werden \(und kann nicht rückgängig gemacht werden\).  
  
 `IRowsetChangeImpl` implementiert die OLE DB\- `IRowsetChange`\-Schnittstelle, die das Aktualisieren von Werten von Spalten in vorhandenen Zeilen, das Löschen von Zeilen und Einfügen von neuen Zeilen aktiviert.  
  
 Die OLE DB\-Vorlagen\-Implementierung unterstützt alle Basismethoden \(`SetData`, `InsertRow` und `DeleteRows`\).  
  
> [!IMPORTANT]
>  VOR Sie versuchen, es wird dringend empfohlen, die der folgenden Dokumentation, den Anbieter zu implementieren lesen:  
  
-   [Erstellen für einen aktualisierbaren Anbieter](../../data/oledb/creating-an-updatable-provider.md)  
  
-   Kapitel 6 *OLE DB Programmer's Reference*  
  
-   Siehe auch, wie die `RUpdateRowset`\-Klasse im UpdatePV\-Beispiel verwendet wird  
  
## Anforderungen  
 **Header:**  atldb.h  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)