---
title: 'CCommand:: Create | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CCommand.Create
- CCommand::Create
dev_langs: C++
helpviewer_keywords: Create method [C++]
ms.assetid: e4bede7a-68bd-491a-97f4-89b03d45cd24
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f4bbd236c2ec7ae6857ede1ac64f738ca8600774
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccommandcreate"></a>CCommand::Create
Aufrufe [CCommand:: CreateCommand](../../data/oledb/ccommand-createcommand.md) So erstellen Sie einen Befehl für die angegebene Sitzung ruft dann [ICommandText:: SetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) den Befehlstext an.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT CCommandBase::Create(  
   const CSession& session,   
   LPCWSTR wszCommand,   
   REFGUID guidCommand = DBGUID_DEFAULT  
) throw ( );  
HRESULT CCommandBase::Create(  
   const CSession& session,   
   LPCSTR szCommand,   
   REFGUID guidCommand = DBGUID_DEFAULT  
) throw ( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `session`  
 [in] Eine Sitzung auf dem Sie den Befehl zu erstellen.  
  
 `wszCommand`  
 [in] Ein Zeiger auf den Unicode-Text der Befehlszeichenfolge.  
  
 `szCommand`  
 [in] Ein Zeiger auf die ANSI-Text der Befehlszeichenfolge.  
  
 `guidCommand`  
 [in] Eine GUID, die Syntax und die allgemeinen Regeln für den zu verwendenden Anbieter angibt, bei der Analyse des Befehlstexts. Eine Beschreibung der Dialekte, finden Sie unter [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Die erste Form der **erstellen** nimmt eine Zeichenfolge der Unicode-Befehl. Die zweite Form der **erstellen** nimmt eine ANSI-Befehl-Zeichenfolge (für Abwärtskompatibilität mit vorhandenen ANSI-Anwendungen bereitgestellt).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CCommand-Klasse](../../data/oledb/ccommand-class.md)