---
title: "CCommand-Klasse"
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
  - "ATL::CCommand"
  - "CCommand"
  - "ATL.CCommand"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCommand-Klasse"
ms.assetid: 0760bfc5-b9ee-4aee-8e54-31bd78714d3a
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CCommand-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt Methoden bereit, um einen Befehl festzulegen und auszuführen.  
  
## Syntax  
  
```  
template <  
   class TAccessor = CNoAccessor,  
   template < typename T > class TRowset = CRowset,  
   class TMultiple = CNoMultipleResults   
>  
class CCommand :   
   public CAccessorRowset <  
      TAccessor,   
      TRowset   
   >,  
   public CCommandBase,  
   public TMultiple  
```  
  
#### Parameter  
 `TAccessor`  
 Der Typ der Accessorklasse \(wie `CDynamicParameterAccessor`, `CDynamicStringAccessor` oder `CEnumeratorAccessor`\) dieser sollten Sie den Befehl zu verwenden.  Der Standard ist `CNoAccessor`, was Parameter oder \-Ausgabespalten der Klasse nicht Stützangibt.  
  
 `TRowset`  
 Der Typ der Rowsetklasse \(wie `CArrayRowset` oder `CNoRowset`\) dieser sollten Sie den Befehl zu verwenden.  Die Standardeinstellung ist `CRowset`.  
  
 `TMultiple`  
 Um einer OLE DB\- verwenden Sie einen EXE\-Befehl die verschiedenen Ergebnisse zurückgeben kann, [CMultipleResults](../../data/oledb/cmultipleresults-class.md) angeben.  Andernfalls wird mithilfe von [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md).  Ausführliche Informationen finden Sie unter [IMultipleResults](https://msdn.microsoft.com/en-us/library/ms721289.aspx).  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[Schließen](../../data/oledb/ccommand-close.md)|Schließt den aktuellen Befehl.|  
|[GetNextResult](../../data/oledb/ccommand-getnextresult.md)|Ruft das folgende Ergebnis, wenn, mehrere Resultsets.|  
|[Öffnen](../../data/oledb/ccommand-open.md)|Führt aus und bindet optional den Befehl.|  
  
### Geerbte Methoden  
  
|||  
|-|-|  
|[Create](../../data/oledb/ccommand-create.md)|Erstellt einen neuen Befehl für die angegebene Sitzung, legt dann den Befehlstext fest.|  
|[CreateCommand](../../data/oledb/ccommand-createcommand.md)|Erstellt einen neuen Befehl.|  
|[GetParameterInfo](../../data/oledb/ccommand-getparameterinfo.md)|Ruft eine Liste der Parameter des Befehls, ihre Namen und ihre Typen ab.|  
|[Vorbereiten vor](../../data/oledb/ccommand-prepare.md)|Überprüft und optimiert den aktuellen Befehl.|  
|[ReleaseCommand](../../data/oledb/ccommand-releasecommand.md)|Befreit den Parameteraccessor ggf., gibt den Befehl frei.|  
|[SetParameterInfo](../../data/oledb/ccommand-setparameterinfo.md)|Gibt dem systemeigenen Typ jedes Befehlsparameters an.|  
|[Unprepare](../../data/oledb/ccommand-unprepare.md)|Gibt den aktuellen Befehlsausführungsplan auf.|  
  
## Hinweise  
 Verwenden Sie diese Klasse, um einen auf Parametern basierenden Vorgang oder einen Befehl auszuführen.  Wenn Sie lediglich ein einfaches Rowset öffnen müssen, verwenden Sie stattdessen [CTable](../../data/oledb/ctable-class.md).  
  
 Die Accessorklasse, die Sie verwenden, bestimmt die Methode von Bindungsparametern und Daten.  
  
 Beachten Sie, dass Sie gespeicherte Prozeduren mit dem OLE DB\-Anbieter für Jet nicht verwenden können, da dieser Anbieter unterstützt keine gespeicherten Prozeduren \(In Abfragezeichenfolgen sind lediglich Konstanten\).  
  
## Anforderungen  
 **Header:**  atldbcli.h  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)