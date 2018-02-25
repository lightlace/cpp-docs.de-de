---
title: CDataConnection-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CDataConnection
- ATL.CDataConnection
- CDataConnection
dev_langs:
- C++
helpviewer_keywords:
- CDataConnection class
ms.assetid: 77432d85-4e20-49ec-a0b0-142137828471
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2c8e405b95543d170a4e94e39626e9b9793791c7
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cdataconnection-class"></a>CDataConnection-Klasse
Verwaltet die Verbindung mit der Datenquelle.  
  
## <a name="syntax"></a>Syntax

```cpp
class CDataConnection  
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CDataConnection](../../data/oledb/cdataconnection-cdataconnection.md)|Konstruktor. Instanziiert und initialisiert ein `CDataConnection` Objekt.|  
|[Kopieren](../../data/oledb/cdataconnection-copy.md)|Erstellt eine Kopie einer vorhandenen Verbindung mit Daten.|  
|[Öffnen](../../data/oledb/cdataconnection-open.md)|Öffnet eine Verbindung mit einer Datenquelle mit einer Initialisierungszeichenfolge an.|  
|[OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md)|Öffnet eine neue Sitzung auf die aktuelle Verbindung an.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator BOOL](../../data/oledb/cdataconnection-operator-bool.md)|Bestimmt, ob die aktuelle Sitzung geöffnet ist.|  
|[operator bool](../../data/oledb/cdataconnection-operator-bool-ole-db.md)|Bestimmt, ob die aktuelle Sitzung geöffnet ist.|  
|[Operator CDataSource &](../../data/oledb/cdataconnection-operator-cdatasource-amp.md)|Gibt einen Verweis auf die enthaltene `CDataSource` Objekt.|  
|[Operator CDataSource *](../../data/oledb/cdataconnection-operator-cdatasource-star.md)|Gibt einen Zeiger auf die enthaltene `CDataSource` Objekt.|  
|[Operator-CSession &](../../data/oledb/cdataconnection-operator-csession-amp.md)|Gibt einen Verweis auf die enthaltene `CSession` Objekt.|  
|[Operator CSession *](../../data/oledb/cdataconnection-operator-csession-star.md)|Gibt einen Zeiger auf die enthaltene `CSession` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CDataConnection` ist eine nützliche für Clients erstellen, da sie kapselt erforderlichen Objekte (Datenquelle und Sitzung), und einige der Aufgaben, die Sie beim Verbinden mit einer Datenquelle ausführen müssen  
  
 Ohne `CDataConnection`, müssen Sie erstellen eine `CDataSource` -Objekt, rufen Sie seine [OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md) -Methode, erstellen Sie eine Instanz von einer [CSession](../../data/oledb/csession-class.md) -Objekt, rufen Sie seine [ Open](../../data/oledb/csession-open.md) -Methode, erstellen Sie dann eine [CCommand](../../data/oledb/ccommand-class.md) Objekt, und rufen die **öffnen*** Methoden.  
  
 Mit `CDataConnection`, müssen Sie nur ein Verbindungsobjekt erstellen Sie eine Initialisierungszeichenfolge zu übergeben, und diese Verbindung verwenden, um Befehle zu öffnen. Wenn Sie die Verbindung mit der Datenbank wiederholt verwenden möchten, ist es ratsam, die Verbindung geöffnet zu halten und `CDataConnection` bietet eine einfache Möglichkeit hierzu.  
  
> [!NOTE]
>  Wenn Sie eine datenbankanwendung, die mehrere Sitzungen verarbeiten muss erstellen, müssen Sie mit [OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)