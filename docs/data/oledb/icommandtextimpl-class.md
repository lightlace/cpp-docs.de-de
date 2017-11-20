---
title: ICommandTextImpl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ICommandText
dev_langs: C++
helpviewer_keywords: ICommandText class
ms.assetid: 9c2715cc-1e55-4468-8327-85341617ed46
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7c3567a16981d4abb16ace70cc2d0509bf9c886e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="icommandtextimpl-class"></a>ICommandTextImpl-Klasse
Stellt eine Implementierung für die [ICommandText](https://msdn.microsoft.com/en-us/library/ms714914.aspx) Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```  
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