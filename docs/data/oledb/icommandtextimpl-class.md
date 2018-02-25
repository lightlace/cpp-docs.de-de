---
title: ICommandTextImpl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ICommandText
dev_langs:
- C++
helpviewer_keywords:
- ICommandText class
ms.assetid: 9c2715cc-1e55-4468-8327-85341617ed46
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c74ad1da299c05ade422596b08d48f33f9d22e37
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="icommandtextimpl-class"></a>ICommandTextImpl-Klasse
Stellt eine Implementierung für die [ICommandText](https://msdn.microsoft.com/en-us/library/ms714914.aspx) Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T >  
class ATL_NO_VTABLE ICommandTextImpl   
   : public ICommandImpl<T, ICommandText>  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Befehlsklasse abgeleitet **ICommandTextImpl**.  
  
## <a name="members"></a>Member  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[GetCommandText](../../data/oledb/icommandtextimpl-getcommandtext.md)|Gibt den Text Befehlssatz, der vom letzten Aufruf von [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md).|  
|[SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md)|Legt den Befehlstext, und Ersetzen Sie dabei die vorhandenen Befehlstext fest.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[m_strCommandText](../../data/oledb/icommandtextimpl-m-strcommandtext.md)|Speichert den Befehlstext an.|  
  
## <a name="remarks"></a>Hinweise  
 Keine verbindliche Schnittstelle für Befehle.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** altdb.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)