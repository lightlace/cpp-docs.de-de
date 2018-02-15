---
title: CCommand-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CCommand
- CCommand
- ATL.CCommand
dev_langs:
- C++
helpviewer_keywords:
- CCommand class
ms.assetid: 0760bfc5-b9ee-4aee-8e54-31bd78714d3a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5ec786bff30745a986ecc643cd42f0d8975b0ccf
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="ccommand-class"></a>CCommand-Klasse
Stellt Methoden zum Festlegen und Ausführen eines Befehls bereit.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class TAccessor = CNoAccessor,  
          template <typename T> class TRowset = CRowset,  
          class TMultiple = CNoMultipleResults>  
class CCommand :   
           public CAccessorRowset <TAccessor, TRowset>,  
           public CCommandBase,  
           public TMultiple  
```  
  
#### <a name="parameters"></a>Parameter  
 `TAccessor`  
 Der Typ der Accessorklasse (z. B. `CDynamicParameterAccessor`, `CDynamicStringAccessor`, oder `CEnumeratorAccessor`), dass Sie den Befehl verwenden möchten. Die Standardeinstellung ist `CNoAccessor`, was bedeutet, dass die Klasse nicht unterstützen Parameter oder Spalten ausgeben.  
  
 `TRowset`  
 Der Typ der Rowsetklasse (z. B. `CArrayRowset` oder `CNoRowset`), dass Sie den Befehl verwenden möchten. Die Standardeinstellung ist `CRowset`.  
  
 `TMultiple`  
 Um einen OLE DB-Befehl verwenden, die mehrere Ergebnisse zurückgegeben werden können, geben [CMultipleResults](../../data/oledb/cmultipleresults-class.md). Verwenden Sie andernfalls [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md). Weitere Informationen finden Sie unter [IMultipleResults](https://msdn.microsoft.com/en-us/library/ms721289.aspx).  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[Schließen](../../data/oledb/ccommand-close.md)|Schließt den aktuellen Befehl an.|  
|[GetNextResult](../../data/oledb/ccommand-getnextresult.md)|Dadurch wird das nächste Ergebnis beim Verwenden von mehreren Resultsets.|  
|[Öffnen](../../data/oledb/ccommand-open.md)|Führt ein, und bindet optional den Befehl.|  
  
### <a name="inherited-methods"></a>Geerbte Methoden  
  
|||  
|-|-|  
|[Create](../../data/oledb/ccommand-create.md)|Erstellt einen neuen Befehl für die angegebene Sitzung, und legt dann den Befehlstext.|  
|[CreateCommand](../../data/oledb/ccommand-createcommand.md)|Erstellt einen neuen Befehl.|  
|[GetParameterInfo](../../data/oledb/ccommand-getparameterinfo.md)|Ruft eine Liste der Parameter des Befehls, ihren Namen und ihre Typen ab.|  
|[Prepare](../../data/oledb/ccommand-prepare.md)|Überprüft, und den aktuellen Befehl optimiert.|  
|[ReleaseCommand](../../data/oledb/ccommand-releasecommand.md)|Bei Bedarf die Parameteraccessor frei, und gibt der Befehl frei.|  
|[SetParameterInfo](../../data/oledb/ccommand-setparameterinfo.md)|Gibt den systemeigenen Typ eines jeden Befehlsparameter.|  
|[Unprepare](../../data/oledb/ccommand-unprepare.md)|Verwirft den aktuellen Befehl Ausführungsplan.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Klasse, wenn Sie einen Parameter-basierte-Vorgang oder einen Befehl ausführen müssen. Wenn Sie nur ein einfaches Rowsets öffnen möchten, verwenden Sie [CTable](../../data/oledb/ctable-class.md) stattdessen.  
  
 Die Accessorklasse, die Sie verwenden bestimmt die Methode der Bindung von Parametern und Daten.  
  
 Beachten Sie, dass Sie gespeicherte Prozeduren mit dem OLE DB-Anbieter für Jet verwenden können, da dieser Anbieter nicht unterstützt gespeicherte Prozeduren, die (nur Konstanten sind in Abfragezeichenfolgen zulässig).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)