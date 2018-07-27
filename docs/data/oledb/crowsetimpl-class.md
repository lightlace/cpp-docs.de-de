---
title: CRowsetImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowsetImpl
- ATL.CRowsetImpl
- ATL::CRowsetImpl
- CRowsetImpl.NameFromDBID
- CRowsetImpl::NameFromDBID
- CRowsetImpl.SetCommandText
- CRowsetImpl::SetCommandText
- GetColumnInfo
- CRowsetImpl.GetColumnInfo
- CRowsetImpl::GetColumnInfo
- CRowsetImpl::GetCommandFromID
- GetCommandFromID
- CRowsetImpl.GetCommandFromID
- CRowsetImpl.ValidateCommandID
- CRowsetImpl::ValidateCommandID
- CRowsetImpl.m_rgRowData
- CRowsetImpl::m_rgRowData
- CRowsetImpl::m_strCommandText
- CRowsetImpl.m_strCommandText
- CRowsetImpl::m_strIndexText
- CRowsetImpl.m_strIndexText
dev_langs:
- C++
helpviewer_keywords:
- CRowsetImpl class
- NameFromDBID method
- SetCommandText method
- GetColumnInfo method
- GetCommandFromID method
- ValidateCommandID method
- m_rgRowData
- m_strCommandText
- m_strIndexText
ms.assetid: e97614b3-b11d-4806-a0d3-b9401331473f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cdd76941a2e91edf598bc5bd354369c849b2dd35
ms.sourcegitcommit: b0d6777cf4b580d093eaf6104d80a888706e7578
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2018
ms.locfileid: "39269702"
---
# <a name="crowsetimpl-class"></a>CRowsetImpl-Klasse
Stellt eine Standardimplementierung der OLE DB-Rowset ohne mehrfache Vererbung von viele Implementierung-Schnittstellen bereit.  
  
## <a name="syntax"></a>Syntax

```cpp
template <  
   class T,  
   class Storage,  
   class CreatorClass,  
   class ArrayType = CAtlArray<Storage>,   
   class RowClass = CSimpleRow,   
   class RowsetInterface = IRowsetImpl <T, IRowset>   
>  
class CRowsetImpl :    
   public CComObjectRootEx<CreatorClass::_ThreadModel>,   
   public CRowsetBaseImpl<T, Storage, ArrayType, RowsetInterface>,   
   public IRowsetInfoImpl<T, CreatorClass::_PropClass>  
```  
  
### <a name="parameters"></a>Parameter  
 *T*  
 Abgeleitete Klasse des Benutzers `CRowsetImpl`.  
  
 *Speicher*  
 Die Benutzerdatensatz-Klasse.  
  
 *CreatorClass*  
 Die Klasse, die Eigenschaften für das Rowset enthält; in der Regel den Befehl.  
  
 *ArrayType*  
 Die Klasse, die als Speicher für Daten, der im Rowset fungiert. Dieser Parameter ist standardmäßig `CAtlArray`, aber es kann sein, alle Klassen, die erforderliche Funktionalität zu unterstützen.  

## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[NameFromDBID](#namefromdbid)|Extrahiert eine Zeichenfolge aus einem `DBID` und kopiert diesen in der *Bstr* übergeben.|  
|[SetCommandText](#setcommandtext)|Überprüft, und speichert die `DBID`s in den beiden Zeichenfolgen ([M_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [M_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)).|  
  
### <a name="overridable-methods"></a>Überschreibbare Methoden  
  
|||  
|-|-|  
|[GetColumnInfo](#getcolumninfo)|Ruft die Spalteninformationen für eine bestimmte Clientanforderung ab.|  
|[GetCommandFromID](#getcommandfromid)|Überprüft, wenn eine oder beide Parameter Werte enthalten, und wenn dies der Fall ist, kopiert die Werte mit den Datenelementen [M_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [M_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).|  
|[ValidateCommandID](#validatecommandid)|Überprüft, zu überprüfen, ob beiden oder beide `DBID`s String-Werte enthalten, und wenn dies der Fall ist, kopiert diese auf seine Datenmember [M_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [M_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[m_rgRowData](#rgrowdata)|Standardmäßig eine `CAtlArray` , die auf das Benutzer Datensätze Vorlagenargument für templatizes `CRowsetImpl`. Ein anderes Array-Typ-Klasse kann verwendet werden, durch Ändern der `ArrayType` Vorlagenargument für `CRowsetImpl`.|  
|[m_strCommandText](#strcommandtext)|Enthält der erste Befehl des Rowsets.|  
|[m_strIndexText](#strindextext)|Enthält das Rowset des anfänglichen Index.|  
  
## <a name="remarks"></a>Hinweise  
 `CRowsetImpl` enthält die Außerkraftsetzungen in Form von statischen werden. Die Methoden steuern die Art und Weise, in der ein angegebenes Rowset Befehlstext überprüft. Können Sie Ihre eigenen erstellen `CRowsetImpl`-Klasse, indem Sie Ihre Implementierung-Schnittstellen machen mehrere geerbte formatieren. Die einzige Methode, die für die Sie bereitstellen müssen, ist der Implementierung `Execute`. Je nach Art des Rowsets Sie erstellen, die Ersteller Methoden erwarten, dass Sie verschiedene Signaturen für `Execute`. Angenommen, Sie verwenden eine `CRowsetImpl`-abgeleitete Klasse, um ein Schemarowset, implementieren die `Execute` Methode wird die folgende Signatur aufweisen:  
  
 `HRESULT Execute(LONG* pcRows, ULONG cRestrictions, const VARIANT* rgRestrictions)`  
  
 Bei der Erstellung einer `CRowsetImpl`-abgeleitete Klasse, um einen Befehl oder Sitzung Rowsets, implementieren die `Execute` Methode hat die folgende Signatur:  
  
 `HRESULT Execute(LONG* pcRows, DBPARAMS* pParams)`  
  
 Zum Implementieren der `CRowsetImpl`-abgeleitete `Execute` Methoden müssen Sie Ihre internen Datenpuffer Auffüllen ([M_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)).  

## <a name="namefromdbid"></a> CRowsetImpl:: Namefromdbid
Extrahiert eine Zeichenfolge aus einem `DBID` und kopiert diesen in der *Bstr* übergeben.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT CRowsetBaseImpl::NameFromDBID(DBID* pDBID,  
   CComBSTR& bstr,  
   bool bIndex);  
```  
  
#### <a name="parameters"></a>Parameter  
 *pDBID*  
 [in] Ein Zeiger auf die `DBID` aus der eine Zeichenfolge zu extrahieren.  
  
 *BSTR*  
 [in] Ein [CComBSTR](../../atl/reference/ccombstr-class.md) Verweis auf eine Kopie des Platzieren der `DBID` Zeichenfolge.  
  
 *bIndex*  
 [in] **"true"** Wenn ein Index `DBID`; **"false"** bei einer Tabelle `DBID`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard-HRESULT. Je nachdem, ob die `DBID` ist eine Tabelle oder eines Indexes (gekennzeichnet durch *bIndex*), die Methode gibt entweder DB_E_NOINDEX oder DB_E_NOTABLE.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem die `CRowsetImpl` Implementierungen von [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) und [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md). 
  
## <a name="setcommandtext"></a> CRowsetImpl:: SetCommandText
Überprüft, und speichert die `DBID`s in den beiden Zeichenfolgen ([M_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [M_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)).  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT CRowsetBaseImpl::SetCommandText(DBID* pTableID,  
   DBID* pIndexID);  
```  
  
#### <a name="parameters"></a>Parameter  
 *pTableID*  
 [in] Ein Zeiger auf die `DBID` , die ID der Tabelle darstellt.  
  
 *pIndexID*  
 [in] Ein Zeiger auf die `DBID` , die Index-ID darstellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard-HRESULT.  
  
### <a name="remarks"></a>Hinweise  
 Die `SetCommentText` Methode wird aufgerufen, indem `CreateRowset`, eine statische vorlagenbasiert-Methode der `IOpenRowsetImpl`.  
  
 Diese Methode delegiert die Arbeit durch Aufrufen von [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) und [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md) über einen upcasted Zeiger. 

## <a name="getcolumninfo"></a> CRowsetImpl:: GetColumnInfo
Ruft die Spalteninformationen für eine bestimmte Clientanforderung ab.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      static ATLCOLUMNINFO* CRowsetBaseImpl::GetColumnInfo(T* pv,  
   ULONG* pcCols);  
```  
  
#### <a name="parameters"></a>Parameter  
 *PV*  
 [in] Ein Zeiger auf das `CRowsetImpl` abgeleitete Klasse.  
  
 *pcCols*  
 [in] Ein Zeiger (Ausgabe), um die Anzahl von Spalten zurückgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein statisches `ATLCOLUMNINFO` Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ist eine erweiterte außer Kraft setzen.  
  
 Diese Methode wird von mehreren basisimplementierung Klassen zum Abrufen der Spalteninformationen für einen bestimmten Client-Anforderung aufgerufen. In der Regel würden diese Methode aufgerufen werden, indem `IColumnsInfoImpl`. Wenn Sie diese Methode überschreiben, müssen Sie eine Version der Methode in Platzieren Ihrer `CRowsetImpl`-abgeleitete Klasse. Da die Methode in einer Klasse nicht auf Vorlagen beruhen platziert werden kann, müssen Sie ändern *pv* an die entsprechende `CRowsetImpl`-abgeleitete Klasse.  
  
 Das folgende Beispiel zeigt `GetColumnInfo` Nutzung. In diesem Beispiel `CMyRowset` ist eine `CRowsetImpl`-abgeleitete Klasse. Um zu überschreiben `GetColumnInfo` für alle Instanzen dieser Klasse, platzieren Sie die folgende Methode in der `CMyRowset` Definition der Klasse:  
  
 [!code-cpp[NVC_OLEDB_Provider#1](../../data/oledb/codesnippet/cpp/crowsetimpl-getcolumninfo_1.h)]  

## <a name="getcommandfromid"></a> CRowsetImpl:: Getcommandfromid
Überprüft, wenn eine oder beide Parameter Werte enthalten, und wenn dies der Fall ist, kopiert die Werte mit den Datenelementen [M_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [M_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT CRowsetBaseImpl::GetCommandFromID(DBID* pTableID,  
   DBID* pIndexID);  
```  
  
#### <a name="parameters"></a>Parameter  
 *pTableID*  
 [in] Ein Zeiger auf die `DBID` darstellt, die Tabelle-ID.  
  
 *pIndexID*  
 [in] Ein Zeiger auf die `DBID` darstellt, der die Index-ID  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard-HRESULT.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, über eine statische Typumwandlung nach oben durch `CRowsetImpl` zum Auffüllen der Datenmember [M_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [M_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md). Diese Methode überprüft standardmäßig angezeigt, wenn eine oder beide Parameter Werte vom Typ String enthalten. Wenn sie Zeichenfolgenwerte enthalten, kopiert diese Methode die Zeichenfolgenwerte mit den Datenelementen. Platzieren Sie eine Methode mit folgender Signatur in Ihrer `CRowsetImpl`-abgeleitete Klasse sein, die Methode wird anstelle von die basisimplementierung aufgerufen werden. 

## <a name="validatecommandid"></a> CRowsetImpl:: ValidateCommandID
Überprüft, zu überprüfen, ob beiden oder beide `DBID`s String-Werte enthalten, und wenn dies der Fall ist, kopiert diese auf seine Datenmember [M_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [M_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT CRowsetBaseImpl::ValidateCommandID(DBID* pTableID,  
   DBID* pIndexID);  
```  
  
#### <a name="parameters"></a>Parameter  
 *pTableID*  
 [in] Ein Zeiger auf die `DBID` , die ID der Tabelle darstellt.  
  
 *pIndexID*  
 [in] Ein Zeiger auf die `DBID` , die Index-ID darstellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard-HRESULT.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, über eine statische Typumwandlung nach oben durch `CRowsetImpl` zum Auffüllen von Datenmembern [M_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [M_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md). Standardmäßig wird diese Methode zum Überprüfen, ob beiden oder beide überprüft `DBID`s String-Werte enthalten, und wenn dies der Fall ist, kopiert diese auf seine Datenmember. Platzieren Sie eine Methode mit folgender Signatur in Ihrer `CRowsetImpl`-abgeleitete Klasse sein, die Methode wird anstelle von die basisimplementierung aufgerufen werden.  

## <a name="rgrowdata"></a> CRowsetImpl:: M_rgrowdata
Standardmäßig eine `CAtlArray` , die auf das Benutzer Datensätze Vorlagenargument für templatizes `CRowsetImpl`.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
ArrayType CRowsetBaseImpl::m_rgRowData;  
  
```  
  
### <a name="remarks"></a>Hinweise  
 *ArrayType* ist ein Vorlagenparameter, `CRowsetImpl`.  

## <a name="strcommandtext"></a> CRowsetImpl:: M_strcommandtext
Enthält der erste Befehl des Rowsets.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
CComBSTR CRowsetBaseImpl::m_strCommandText;  
  
```  

## <a name="strindextext"></a> CRowsetImpl:: M_strindextext
Enthält das Rowset des anfänglichen Index.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
CComBSTR CRowsetBaseImpl::m_strIndexText;  
  
```  
