---
title: "CMyProviderRowset (MyProviderRS.H)"
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
  - "cmyproviderrowset"
  - ""myproviderrs.h""
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMyProviderRowset Klasse in MyProviderRS.H"
  - "OLE DB-Anbieter, Assistentengenerierte Dateien"
ms.assetid: 7ba1a124-3842-40eb-a36b-302190a1af3a
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CMyProviderRowset (MyProviderRS.H)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Assistent generiert einen Eintrag für das Rowsetobjekt.  In diesem Fall erhält das Objekt die Bezeichnung `CMyProviderRowset`.  Die `CMyProviderRowset`\-Klasse erbt von einer OLE DB\-Anbieterklasse mit dem Namen `CRowsetImpl`, die alle für das Rowsetobjekt erforderlichen Schnittstellen implementiert.  Der folgende Code veranschaulicht die Vererbungskette für `CRowsetImpl`:  
  
```  
template <class T, class Storage, class CreatorClass,   
   class ArrayType = CAtlArray<Storage> >  
class CMyRowsetImpl:  
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType,   
      CSimpleRow, IRowsetLocateImpl< T > >  
```  
  
 `CRowsetImpl` verwendet außerdem die Schnittstellen `IAccessor` und `IColumnsInfo`.  Diese Schnittstellen werden für Ausgabefelder in Tabellen verwendet.  Die Klasse bietet auch eine Implementierung für **IRowsetIdentity**. Hiermit kann der Consumer ermitteln, ob zwei Zeilen identisch sind.  Die Eigenschaften des Rowsetobjekts werden von der `IRowsetInfo`\-Schnittstelle implementiert.  Durch die **IConvertType**\-Schnittstelle kann der Anbieter Differenzen zwischen Datentypen auflösen, die vom Consumer angefordert und vom Anbieter verwendet werden.  
  
 Die `IRowset`\-Schnittstelle ist derzeit für die Verwaltung von Datenabrufen verantwortlich.  Zunächst ruft der Consumer eine Methode mit der Bezeichnung `GetNextRows` auf, um ein Handle für eine Zeile, das so genannte **HROW**, zurückzugeben.  Anschließend ruft er **IRowset::GetData** mit dem oben genannten **HROW** auf, um die angeforderten Daten abzurufen.  
  
 `CRowsetImpl` verfügt auch über einige Vorlagenparameter.  Mit diesen Parametern können Sie bestimmen, auf welche Weise Daten von der `CRowsetImpl`\-Klasse verarbeitet werden.  Mithilfe des `ArrayType`\-Arguments können Sie festlegen, welcher Speichermechanismus zum Speichern der Zeilendaten verwendet wird.  Der **RowClass**\-Parameter gibt an, in welcher Klasse ein **HROW** enthalten ist.  
  
 Der **RowsetInterface**\-Parameter ermöglicht zusätzlich die Verwendung der `IRowsetLocate`\-Schnittstelle oder der `IRowsetScroll`\-Schnittstelle.  Die Schnittstellen `IRowsetLocate` und `IRowsetScroll` erben beide von `IRowset`.  Aus diesem Grund müssen diese Schnittstellen von den OLE DB\-Anbietervorlagen gesondert behandelt werden.  Wenn Sie eine dieser Schnittstellen verwenden möchten, muss dieser Parameter angegeben werden.  
  
## Siehe auch  
 [Vom Anbieter\-Assistenten generierte Dateien](../../data/oledb/provider-wizard-generated-files.md)