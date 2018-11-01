---
title: ICommandTextImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- ICommandText
- GetCommandText
- ICommandTextImpl.GetCommandText
- ICommandTextImpl::GetCommandText
- ATL::ICommandTextImpl::m_strCommandText
- ICommandTextImpl<T>::m_strCommandText
- m_strCommandText
- ICommandTextImpl.m_strCommandText
- ICommandTextImpl::m_strCommandText
- ATL::ICommandTextImpl<T>::m_strCommandText
- ATL.ICommandTextImpl.m_strCommandText
- ICommandTextImpl.SetCommandText
- ICommandTextImpl::SetCommandText
- SetCommandText
helpviewer_keywords:
- ICommandText class
- GetCommandText method
- m_strCommandText
- SetCommandText method
ms.assetid: 9c2715cc-1e55-4468-8327-85341617ed46
ms.openlocfilehash: fafd1198776c558ff39ef35c0b7beca538e976ae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677694"
---
# <a name="icommandtextimpl-class"></a>ICommandTextImpl-Klasse

Stellt eine Implementierung für die [ICommandText](/previous-versions/windows/desktop/ms714914) Schnittstelle.

## <a name="syntax"></a>Syntax

```cpp
template <class T >
class ATL_NO_VTABLE ICommandTextImpl
   : public ICommandImpl<T, ICommandText>
```

### <a name="parameters"></a>Parameter

*T*<br/>
Die Befehlsklasse abgeleitet `ICommandTextImpl`.

## <a name="requirements"></a>Anforderungen

**Header:** altdb.h

## <a name="members"></a>Member

### <a name="interface-methods"></a>Schnittstellenmethoden

|||
|-|-|
|[GetCommandText](#getcommandtext)|Gibt den Textbefehl festlegen, indem dem letzten Aufruf von [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md).|
|[SetCommandText](#setcommandtext)|Legt den Befehlstext, und Ersetzen Sie dabei die vorhandenen Befehlstext fest.|

### <a name="data-members"></a>Datenmember

|||
|-|-|
|[m_strCommandText](#strcommandtext)|Speichert den Befehlstext an.|

## <a name="remarks"></a>Hinweise

Eine erforderliche Schnittstelle für Befehle.

## <a name="getcommandtext"></a> ICommandTextImpl:: Getcommandtext

Gibt den Textbefehl festlegen, indem dem letzten Aufruf von [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md).

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(GetCommandText)(GUID * pguidDialect, 
   LPOLESTR * ppwszCommand);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709825) in die *OLE DB-Programmierreferenz*. Die *PguidDialect* Parameter standardmäßig ignoriert.

## <a name="setcommandtext"></a> ICommandTextImpl:: SetCommandText

Legt den Befehlstext, und Ersetzen Sie dabei die vorhandenen Befehlstext fest.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(SetCommandText)(REFGUID rguidDialect, 
   LPCOLESTR pwszCommand);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [ICommandText:: SetCommandText](/previous-versions/windows/desktop/ms709757) in die *OLE DB-Programmierreferenz*.

## <a name="strcommandtext"></a> ICommandTextImpl:: M_strcommandtext

Speichert die Textzeichenfolge für den Befehl.

### <a name="syntax"></a>Syntax

```cpp
CComBSTR m_strCommandText;
```

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)