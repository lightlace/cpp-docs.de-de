---
title: "CRowsetImpl-Klasse"
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
  - "CRowsetImpl"
  - "ATL.CRowsetImpl"
  - "ATL::CRowsetImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRowsetImpl-Klasse"
ms.assetid: e97614b3-b11d-4806-a0d3-b9401331473f
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CRowsetImpl-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Standard\-OLEDB\-Rowsetimplementierung bereit, ohne viele Implementierungsschnittstellen Mehrfachvererbung zu erfordern.  
  
## Syntax  
  
```  
template <  
   class T,  
   class Storage,  
   class CreatorClass,  
   class ArrayType = CAtlArray<Storage>,   
   class RowClass = CSimpleRow,   
   class RowsetInterface = IRowsetImpl < T, IRowset >   
>  
class CRowsetImpl :    
   public CComObjectRootEx<CreatorClass::_ThreadModel>,   
   public CRowsetBaseImpl<T, Storage, ArrayType, RowsetInterface>,   
   public IRowsetInfoImpl<T, CreatorClass::_PropClass>  
```  
  
#### Parameter  
 `T`  
 Die Klasse des Benutzers, die von `CRowsetImpl` abgeleitet.  
  
 `Storage`  
 Die Benutzerdatensatz\-Klasse.  
  
 `CreatorClass`  
 Die Klasse, die Eigenschaften für das Rowset enthält; in der Regel der Befehl.  
  
 `ArrayType`  
 Die Klasse, die als Speicher für die Daten eines Rowsets auftritt.  Dieser Parameter führt zu `CAtlArray`, kann jedoch eine Klasse sein, die die erforderliche Funktionalität unterstützt.  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[NameFromDBID](../../data/oledb/crowsetimpl-namefromdbid.md)|Extrahiert eine Zeichenfolge von **DBID** und kopiert sie auf `bstr`, das übergeben wird.|  
|[SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)|Überprüft Anschließend wird das **DBID**s in beiden Zeichenfolgen \([m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)\).|  
  
### Überschreibbare Methoden  
  
|||  
|-|-|  
|[GetColumnInfo](../../data/oledb/crowsetimpl-getcolumninfo.md)|Ruft Spalteninformationen für eine bestimmte Clientanforderung ab.|  
|[GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md)|Überprüft, um, wenn einer oder beide Parameter Zeichenfolgenwerte enthalten, und wenn ja Kopien, die Zeichenfolgenwerte in den Datenmember [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).|  
|[ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md)|Überprüft, überprüft, ob jedes oder sowohl **DBID**s Zeichenfolgenwerte und wenn ja enthalten, kopiert sie den Datenmember [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).|  
  
### Datenmember  
  
|||  
|-|-|  
|[m\_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)|Standardmäßig `CAtlArray`, das auf dem Benutzerdatensatzvorlagenargument zu `CRowsetImpl` templatizes.  Eine andere Arraytypklasse kann verwendet werden, indem das Vorlagenargument `ArrayType` in `CRowsetImpl` ändert.|  
|[m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)|Enthält den ursprünglichen Befehl des Rowsets.|  
|[m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)|Enthält den ursprünglichen Index des Rowsets.|  
  
## Hinweise  
 `CRowsetImpl` stellt Überschreibungen in Form von statischen Aufwärtsumwandlungen bereit.  Die Methoden steuern die Art, in der ein bestimmtes Rowset Befehlstext überprüft.  Sie können eine eigene Klasse als `CRowsetImpl` erstellen, indem Sie die Mehrfachverbindungsstelle\-geerbten Implementierungsschnittstellen machen.  Die einzige Methode, für die Sie die Implementierung bereitstellen müssen, ist **Ausführen**.  Je nachdem, welcher Typ des Rowsets Sie erstellen, wird die Erstellermethoden unterschiedliche Signaturen für **Ausführen**.  Wenn Sie `CRowsetImpl`\- zu implementieren die abgeleitete Klasse, hat ein Schemarowset, die **Ausführen**\-Methode folgende Signatur:  
  
 `HRESULT Execute(LONG* pcRows, ULONG cRestrictions, const VARIANT* rgRestrictions)`  
  
 Wenn Sie `CRowsetImpl`\- implementiert erstellen die abgeleitete Klasse, hat ein Befehls\- oder Sitzungsrowset, die **Ausführen**\-Methode folgende Signatur:  
  
 `HRESULT Execute(LONG* pcRows, DBPARAMS* pParams)`  
  
 Wenn Sie einen `CRowsetImpl` implementieren abgeleitete **Ausführen**\-Methoden, müssen Sie die internen Datenpuffer \([m\_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)\) füllen.  
  
## Anforderungen  
 **Header:** atldb.h