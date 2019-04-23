---
title: CEnumerator-Klasse
ms.date: 11/04/2016
f1_keywords:
- CEnumerator
- CEnumerator::Find
- ATL::CEnumerator::Find
- ATL.CEnumerator.Find
- CEnumerator.Find
- GetMoniker
- CEnumerator.GetMoniker
- CEnumerator::GetMoniker
- ATL.CEnumerator.GetMoniker
- ATL::CEnumerator::GetMoniker
- ATL.CEnumerator.Open
- CEnumerator::Open
- ATL::CEnumerator::Open
- CEnumerator.Open
helpviewer_keywords:
- CEnumerator class
- Find method
- GetMoniker method
- Open method
ms.assetid: 25805f1b-26e3-402f-af83-1b5fe5ddebf7
ms.openlocfilehash: 23467caf46d38175a74dab061f60e11009f1f481
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59030179"
---
# <a name="cenumerator-class"></a>CEnumerator-Klasse

Verwendet eine OLE DB-Enumerator-Objekt, das macht der [ISourcesRowset](/previous-versions/windows/desktop/ms715969(v=vs.85)) -Schnittstelle zur Rückgabe eines Rowsets, die alle Datenquellen und Enumeratoren beschreibt.

## <a name="syntax"></a>Syntax

```cpp
class CEnumerator :
   public CAccessorRowset< CAccessor <CEnumeratorAccessor >>
```

## <a name="requirements"></a>Anforderungen

**Header:** atldbcli.h

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[Find](#find)|Durchsucht verfügbare Anbieter (Datenquellen) mit dem angegebenen Namen gesucht.|
|[GetMoniker](#getmoniker)|Ruft die `IMoniker` Schnittstelle für den aktuellen Datensatz.|
|[Öffnen](#open)|Öffnet den Enumerator.|

## <a name="remarks"></a>Hinweise

Sie können abrufen, die `ISourcesRowset` Daten, die indirekt von dieser Klasse.

## <a name="find"></a> CEnumerator:: Find

Sucht nach einem angegebenen Namen unter verfügbaren Anbietern.

### <a name="syntax"></a>Syntax

```cpp
bool Find(TCHAR* szSearchName) throw();
```

#### <a name="parameters"></a>Parameter

*szSearchName*<br/>
[in] Der zu suchende Name.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn der Name gefunden wurde. Andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Dieser Name zugeordnet wird, um die `SOURCES_NAME` Mitglied der [ISourcesRowset](/previous-versions/windows/desktop/ms715969(v=vs.85)) Schnittstelle.

## <a name="getmoniker"></a> CEnumerator::GetMoniker

Analysiert den Anzeigenamen die Komponente der Zeichenfolge zu extrahieren, die in einen Moniker konvertiert werden kann.

### <a name="syntax"></a>Syntax

```cpp
HRESULT GetMoniker(LPMONIKER* ppMoniker) const throw();

HRESULT GetMoniker(LPMONIKER* ppMoniker,
   LPCTSTR lpszDisplayName) const throw();
```

#### <a name="parameters"></a>Parameter

*ppMoniker*<br/>
[out] Der Moniker analysiert wird, aus dem Anzeigenamen ([cenumeratoraccessor:: M_szparsename](../../data/oledb/cenumeratoraccessor-m-szparsename.md)) der aktuellen Zeile.

*lpszDisplayName*<br/>
[in] Der Anzeigename analysiert werden soll.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

## <a name="open"></a> CEnumerator:: Open

Den Moniker für den Enumerator, gebunden wird, wenn eine angegeben ist und ruft dann das Rowset für den Enumerator durch Aufrufen von [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)).

### <a name="syntax"></a>Syntax

```cpp
HRESULT Open(LPMONIKER pMoniker) throw();

HRESULT Open(const CLSID* pClsid = & CLSID_OLEDB_ENUMERATOR) throw();

HRESULT Open(const CEnumerator& enumerator) throw();
```

#### <a name="parameters"></a>Parameter

*pMoniker*<br/>
[in] Ein Zeiger auf eine der Moniker für die ein Enumerator.

*pClsid*<br/>
[in] Ein Zeiger auf die `CLSID` eines Enumerators.

*enumerator*<br/>
[in] Ein Verweis auf einen Enumerator.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

## <a name="see-also"></a>Siehe auch

[DBViewer](../../overview/visual-cpp-samples.md)<br/>
[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)