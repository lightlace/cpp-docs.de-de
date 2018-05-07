---
title: 'CDataConnection:: CDataConnection | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataConnection.CDataConnection
- ATL.CDataConnection.CDataConnection
- CDataConnection::CDataConnection
- ATL::CDataConnection::CDataConnection
dev_langs:
- C++
helpviewer_keywords:
- CDataConnection class, constructor
ms.assetid: ac25c9a0-44d3-4083-b13f-76c07772e12d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 267341f88886f3ff94a6b828034e8acbaa2dc0c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cdataconnectioncdataconnection"></a>CDataConnection::CDataConnection
Instanziiert und initialisiert ein `CDataConnection` Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      CDataConnection();   

CDataConnection(const CDataConnection &ds);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ds`  
 [in] Ein Verweis auf eine vorhandene Datenverbindung.  
  
## <a name="remarks"></a>Hinweise  
 Die erste Außerkraftsetzung erstellt ein neues `CDataConnection` Objekt mit den Standardeinstellungen.  
  
 Die zweite Außerkraftsetzung erstellt ein neues `CDataConnection` Objekt mit Einstellungen entspricht dem Datenverbindungsobjekt, die Sie angeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDataConnection-Klasse](../../data/oledb/cdataconnection-class.md)