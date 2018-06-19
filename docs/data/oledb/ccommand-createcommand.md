---
title: 'CCommand:: CreateCommand | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CCommand.CreateCommand
- CreateCommand
- CCommand::CreateCommand
dev_langs:
- C++
helpviewer_keywords:
- CreateCommand method
ms.assetid: 3652a313-07a1-40ec-82d6-fc7182f2a6f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ea3e83c860688d206fae69462b8cb25fb215d8ec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093786"
---
# <a name="ccommandcreatecommand"></a>CCommand::CreateCommand
Erstellt einen neuen Befehl.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT CCommandBase::CreateCommand(const CSession& session) throw ();  
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