---
title: 'CCommand:: CreateCommand | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CCommand.CreateCommand
- CreateCommand
- CCommand::CreateCommand
dev_langs: C++
helpviewer_keywords: CreateCommand method
ms.assetid: 3652a313-07a1-40ec-82d6-fc7182f2a6f6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ce793d4238a043dc7567ac5f003ff8872094d26f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccommandcreatecommand"></a>CCommand::CreateCommand
Erstellt einen neuen Befehl.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT CCommandBase::CreateCommand(  
   const CSession& session   
) throw ( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `session`  
 [in] Ein `CSession` Objekt an den neuen Befehl zugeordnet werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode erstellt einen Befehl mit dem angegebenen Sitzungsobjekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CCommand-Klasse](../../data/oledb/ccommand-class.md)