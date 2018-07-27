---
title: ICommandTextImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- ICommandText class
- GetCommandText method
- m_strCommandText
- SetCommandText method
ms.assetid: 9c2715cc-1e55-4468-8327-85341617ed46
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2223958f2f5dbacb7c86bf2735c1de3a85d9d488
ms.sourcegitcommit: b0d6777cf4b580d093eaf6104d80a888706e7578
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2018
ms.locfileid: "39269490"
---
# <a name="icommandtextimpl-class"></a>ICommandTextImpl-Klasse
Stellt eine Implementierung für die [ICommandText](https://msdn.microsoft.com/library/ms714914.aspx) Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T >  
class ATL_NO_VTABLE ICommandTextImpl   
   : public ICommandImpl<T, ICommandText>  
```  
  
### <a name="parameters"></a>Parameter  
 *T*  
 Die Befehlsklasse abgeleitet **ICommandTextImpl**. 

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
 Finden Sie unter [ICommandText::GetCommandText](https://msdn.microsoft.com/library/ms709825.aspx) in die *OLE DB-Programmierreferenz*. Die *PguidDialect* Parameter standardmäßig ignoriert.  

## <a name="setcommandtext"></a> ICommandTextImpl:: SetCommandText
Legt den Befehlstext, und Ersetzen Sie dabei die vorhandenen Befehlstext fest.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(SetCommandText)(REFGUID rguidDialect,   
   LPCOLESTR pwszCommand);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [ICommandText:: SetCommandText](https://msdn.microsoft.com/library/ms709757.aspx) in die *OLE DB-Programmierreferenz*. 

## <a name="strcommandtext"></a> ICommandTextImpl:: M_strcommandtext
Speichert die Textzeichenfolge für den Befehl.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
CComBSTR m_strCommandText;  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)
