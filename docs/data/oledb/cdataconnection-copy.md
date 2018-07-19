---
title: 'CDataConnection:: Copy | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataConnection.Copy
- ATL.CDataConnection.Copy
- ATL::CDataConnection::Copy
- CDataConnection::Copy
dev_langs:
- C++
helpviewer_keywords:
- Copy method
ms.assetid: a3dbd70d-36be-49e0-a527-00e3910a7a56
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d9264b29a0a5a5df3b80434e0977431fa16ba24a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096167"
---
# <a name="cdataconnectioncopy"></a>CDataConnection::Copy
Erstellt eine Kopie einer vorhandenen Verbindung mit Daten.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      CDataConnection& Copy(const CDataConnection & ds) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `ds`  
 [in] Ein Verweis auf eine vorhandene Datenverbindung zu kopieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDataConnection-Klasse](../../data/oledb/cdataconnection-class.md)