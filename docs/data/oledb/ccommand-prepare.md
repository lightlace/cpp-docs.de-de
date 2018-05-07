---
title: 'CCommand:: Prepare | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CCommand.Prepare
- CCommand::Prepare
- Prepare
dev_langs:
- C++
helpviewer_keywords:
- Prepare method
ms.assetid: f0e473fc-2f7a-4d29-96c2-1328dc21e702
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7d029664508b6be71348aa3aa8d5801191f2aca3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ccommandprepare"></a>CCommand::Prepare
Überprüft, und den aktuellen Befehl optimiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT CCommandBase::Prepare(ULONG cExpectedRuns = 0) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 *cExpectedRuns*  
 [in] Die Anzahl der Wiederholungen, die Sie erwarten, beim Ausführen des Befehls dass.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode dient als Wrapper für die OLE DB-Methode [ICommandPrepare:: Prepare](https://msdn.microsoft.com/en-us/library/ms718370.aspx).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CCommand-Klasse](../../data/oledb/ccommand-class.md)