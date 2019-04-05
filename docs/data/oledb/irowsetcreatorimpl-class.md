---
title: IRowsetCreatorImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- ATL::IRowsetCreatorImpl
- ATL.IRowsetCreatorImpl
- ATL::IRowsetCreatorImpl<T>
- ATL.IRowsetCreatorImpl<T>
- IRowsetCreatorImpl
- IRowsetCreatorImpl.SetSite
- IRowsetCreatorImpl<T>::SetSite
- IRowsetCreatorImpl::SetSite
- SetSite
- ATL.IRowsetCreatorImpl.SetSite
- ATL::IRowsetCreatorImpl<T>::SetSite
- ATL::IRowsetCreatorImpl::SetSite
- ATL.IRowsetCreatorImpl<T>.SetSite
helpviewer_keywords:
- IRowsetCreatorImpl class
- SetSite method
ms.assetid: 92cc950f-7978-4754-8d9a-defa63867d82
ms.openlocfilehash: 3dc5cb06b3eb7f01667e4e1ec09dd60f9befae77
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026603"
---
# <a name="irowsetcreatorimpl-class"></a>IRowsetCreatorImpl-Klasse

Führt die gleichen Funktionen wie `IObjectWithSite` kann jedoch auch die OLE DB-Eigenschaften `DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS`.

## <a name="syntax"></a>Syntax

```cpp
template < class T >
class ATL_NO_VTABLE IRowsetCreatorImpl
   : public IObjectWithSiteImpl< T >
```

### <a name="parameters"></a>Parameter

*T*<br/>
Eine abgeleitete Klasse `IRowsetCreator`.

## <a name="requirements"></a>Anforderungen

**Header:** „atldb.h“

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[SetSite](#setsite)|Legt fest, die Website, die Rowset-Objekt enthält.|

## <a name="remarks"></a>Hinweise

Diese Klasse erbt von [IObjectWithSite](/windows/desktop/api/ocidl/nn-ocidl-iobjectwithsite) und überschreibt [IObjectWithSite::SetSite](/windows/desktop/api/ocidl/nf-ocidl-iobjectwithsite-setsite). Wenn ein Befehl oder Sitzung Anbieterobjekt ein Rowset erstellt wird, ruft er `QueryInterface` für das Rowsetobjekt, das nach `IObjectWithSite` und ruft `SetSite` übergeben des Rowsetobjekt, das die `IUnkown` Schnittstelle wie die Website-Schnittstelle.

## <a name="setsite"></a> IRowsetCreatorImpl::SetSite

Legt fest, die Website, die Rowset-Objekt enthält. Weitere Informationen finden Sie unter [IObjectWithSite::SetSite](/windows/desktop/api/ocidl/nf-ocidl-iobjectwithsite-setsite).

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(SetSite )(IUnknown* pCreator);
```

#### <a name="parameters"></a>Parameter

*pCreator*<br/>
[in] Zeiger auf die `IUnknown` Schnittstellenzeiger auf der Website verwalten von Rowset-Objekt.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

### <a name="remarks"></a>Hinweise

Darüber hinaus `IRowsetCreatorImpl::SetSite` ermöglicht OLE DB- `DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS` Eigenschaften.

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)