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
ms.openlocfilehash: e190f81c0097e707830f7ac09c801929ea3e85e9
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42575488"
---
# <a name="icommandtextimpl-class"></a>ICommandTextImpl-Klasse
Stellt eine Implementierung für die [ICommandText](/previous-versions/windows/desktop/ms714914\(v=vs.85\)) Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T >  
class ATL_NO_VTABLE ICommandTextImpl   
   : public ICommandImpl<T, ICommandText>  
```  
  
### <a name="parameters"></a>Parameter  
 *T*  
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
 Finden Sie unter [ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709825\(v=vs.85\)) in die *OLE DB-Programmierreferenz*. Die *PguidDialect* Parameter standardmäßig ignoriert.  

## <a name="setcommandtext"></a> ICommandTextImpl:: SetCommandText
Legt den Befehlstext, und Ersetzen Sie dabei die vorhandenen Befehlstext fest.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
STDMETHOD(SetCommandText)(REFGUID rguidDialect,   
   LPCOLESTR pwszCommand);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [ICommandText:: SetCommandText](/previous-versions/windows/desktop/ms709757\(v=vs.85\)) in die *OLE DB-Programmierreferenz*. 

## <a name="strcommandtext"></a> ICommandTextImpl:: M_strcommandtext
Speichert die Textzeichenfolge für den Befehl.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
CComBSTR m_strCommandText;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)