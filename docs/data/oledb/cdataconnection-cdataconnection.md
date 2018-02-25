---
title: 'CDataConnection:: CDataConnection | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4405e0dce66de9f006a23b5b680072b9562af06f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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