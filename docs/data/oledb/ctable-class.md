---
title: CTable-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CTable
- ATL.CTable
- CTable
- ATL.CTable.Open
- ATL::CTable::Open
- CTable::Open
- CTable.Open
dev_langs:
- C++
helpviewer_keywords:
- CTable class
- Open method
ms.assetid: f13fdaa3-e198-4557-977d-54b0bbc3454d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 34eb8cb8a6b839f8a4dcd8d699c7fcb4851d57f6
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42572278"
---
# <a name="ctable-class"></a>CTable-Klasse
Bietet eine Möglichkeit, direkt auf ein einfaches Rowset (ohne Parameter) zuzugreifen.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class TAccessor = CNoAccessor, 
            template <typename T> class TRowset = CRowset>  
class CTable :  
   public CAccessorRowset <TAccessor, TRowset>  
```  
  
### <a name="parameters"></a>Parameter  
 *TAccessor*  
 Ein Accessor-Klasse.  
  
 *TRowset*  
 Eine Rowset-Klasse.  

## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[Öffnen](#open)|Öffnet die Tabelle.|  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter [CCommand](../../data/oledb/ccommand-class.md) Informationen zum Ausführen eines Befehls in ein Rowset zugreifen.  

## <a name="open"></a> CTable:: Open
Öffnet die Tabelle.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT Open(const CSession& session,  
   LPCWSTR wszTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0) throw ();  

HRESULT Open(const CSession& session,  
   LPCSTR szTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0) throw ();  

HRESULT Open(const CSession& session,  
   DBID& dbid,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0) throw ();  
```  
  
#### <a name="parameters"></a>Parameter  
 *Sitzung*  
 [in] Die Sitzung, für die in der Tabelle geöffnet wird.  
  
 *wszTableName*  
 [in] Der Name der Tabelle zu öffnen, werden als Unicode-Zeichenfolge übergeben.  
  
 *szTableName*  
 [in] Der Name der Tabelle zu öffnen, werden als eine ANSI-Zeichenfolge übergeben.  
  
 *dbid*  
 [in] Die `DBID` der Tabelle zu öffnen.  
  
 *pPropSet*  
 [in] Ein Zeiger auf ein Array von [DBPROPSET](/previous-versions/windows/desktop/ms714367\(v=vs.85\)) Strukturen, die Eigenschaften und Werte festgelegt werden. Finden Sie unter [Eigenschaftensätze und Eigenschaftengruppen](/previous-versions/windows/desktop/ms713696\(v=vs.85\)) in die *OLE DB-Programmierreferenz* in das Windows SDK. Der Standardwert NULL gibt an, keine Eigenschaften.  
  
 *ulPropSets*  
 [in] Die Anzahl der [DBPROPSET](/previous-versions/windows/desktop/ms714367\(v=vs.85\)) Strukturen zu übergeben, der *DBPROPSET* Argument.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard-HRESULT.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [IOpenRowset:: OPENROWSET](/previous-versions/windows/desktop/ms716724\(v=vs.85\)) in die *OLE DB-Programmierreferenz*.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)   