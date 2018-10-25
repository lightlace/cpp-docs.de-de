---
title: CDataConnection-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CDataConnection
- ATL.CDataConnection
- CDataConnection
- CDataConnection.CDataConnection
- ATL.CDataConnection.CDataConnection
- CDataConnection::CDataConnection
- ATL::CDataConnection::CDataConnection
- CDataConnection.Copy
- ATL.CDataConnection.Copy
- ATL::CDataConnection::Copy
- CDataConnection::Copy
- CDataConnection.Open
- ATL.CDataConnection.Open
- CDataConnection::Open
- ATL::CDataConnection::Open
- CDataConnection.OpenNewSession
- ATL.CDataConnection.OpenNewSession
- ATL::CDataConnection::OpenNewSession
- OpenNewSession
- CDataConnection::OpenNewSession
- CDataConnection::operatorBOOL
- ATL::CDataConnection::operatorBOOL
- CDataConnection.operatorBOOL
- ATL.CDataConnection.operatorBOOL
- CDataConnection::operatorBOOL
- ATL::CDataConnection::operatorBOOL
- CDataConnection.operatorBOOL
- ATL.CDataConnection.operatorBOOL
- CDataSource&
- CDataConnection.operatorCDataSource&
- operatorCDataSource&
- CDataConnection::operatorCDataSource&
- CDataSource*
- CDataConnection::operatorCDataSource*
- CDataConnection.operatorCDataSource*
- operatorCDataSource*
- CSession&
- CDataConnection::operatorCSession&
- CDataConnection.operatorCSession&
- operatorCSession&
- CDataConnection.operatorCSession*
- CDataConnection::operatorCSession*
- operatorCSession*
- CSession*
dev_langs:
- C++
helpviewer_keywords:
- CDataConnection class
- CDataConnection class, constructor
- Copy method
- Open method
- OpenNewSession method
- BOOL operator
- operator bool
- BOOL operator
- operator bool
- CDataSource& operator
- operator & (CDataSource)
- CDataSource* operator
- operator * (CDataSource)
- operator CSession&
- CSession& operator
- operator CSession*
- CSession* operator
ms.assetid: 77432d85-4e20-49ec-a0b0-142137828471
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 07d91cbefcb70fbbb935e29d972f45a9e4cb7376
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50063561"
---
# <a name="cdataconnection-class"></a>CDataConnection-Klasse

Verwaltet die Verbindung mit der Datenquelle an.

## <a name="syntax"></a>Syntax

```cpp
class CDataConnection
```

## <a name="requirements"></a>Anforderungen

**Header:** atldbcli.h

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[CDataConnection](#cdataconnection)|Konstruktor. Instanziiert und initialisiert ein `CDataConnection` Objekt.|
|[Kopieren](#copy)|Erstellt eine Kopie einer vorhandenen Datenverbindung an.|
|[Öffnen](#open)|Öffnet eine Verbindung mit einer Datenquelle mit einer Initialisierungszeichenfolge an.|
|[OpenNewSession](#opennewsession)|Öffnet eine neue Sitzung auf die aktuelle Verbindung an.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[Operator BOOL](#op_bool)|Bestimmt, ob die aktuelle Sitzung geöffnet oder nicht ist.|
|[operator bool](#op_bool_ole)|Bestimmt, ob die aktuelle Sitzung geöffnet oder nicht ist.|
|[Operator CDataSource &](#op_cdata_amp)|Gibt einen Verweis auf die enthaltene `CDataSource` Objekt.|
|[Operator CDataSource *](#op_cdata_star)|Gibt einen Zeiger auf die enthaltene `CDataSource` Objekt.|
|[Operator-CSession &](#op_csession_amp)|Gibt einen Verweis auf die enthaltene `CSession` Objekt.|
|[Operator CSession *](#op_csession_star)|Gibt einen Zeiger auf die enthaltene `CSession` Objekt.|

## <a name="remarks"></a>Hinweise

`CDataConnection` ist eine nützliche für Clients erstellen, da er kapselt erforderlichen Objekte (Datenquelle und Sitzung) und einige der Aufgaben, die Sie tun, wenn eine Verbindung mit einer Datenquelle herstellen möchten

Ohne `CDataConnection`, müssen Sie erstellen eine `CDataSource` Objekt, rufen Sie die [OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md) -Methode, erstellen Sie dann eine Instanz von einer [CSession](../../data/oledb/csession-class.md) Objekt, rufen Sie die [ Open](../../data/oledb/csession-open.md) -Methode, erstellen Sie dann eine [CCommand](../../data/oledb/ccommand-class.md) Objekt, und rufen die `Open`* Methoden.

Mit `CDataConnection`, müssen Sie nur ein Verbindungsobjekt zu erstellen, übergeben es mit einer Initialisierungszeichenfolge, und verwenden diese Verbindung, um Befehle zu öffnen. Wenn Sie die Verbindung mit der Datenbank immer wieder verwenden möchten, ist es eine gute Idee, die Verbindung geöffnet zu halten und `CDataConnection` bietet eine bequeme Möglichkeit dazu.

> [!NOTE]
>  Wenn Sie eine datenbankanwendung, die mehrere Sitzungen verarbeiten muss erstellen, müssen Sie mit [OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md).

## <a name="#cdataconnection"></a> CDataConnection:: CDataConnection

Instanziiert und initialisiert ein `CDataConnection` Objekt.

### <a name="syntax"></a>Syntax

```cpp
CDataConnection(); 
CDataConnection(const CDataConnection &ds);
```

#### <a name="parameters"></a>Parameter

*DS*<br/>
[in] Ein Verweis auf eine vorhandene Datenverbindung.

### <a name="remarks"></a>Hinweise

Beim ersten überschreiben erstellt ein neues `CDataConnection` -Objekt mit Standardeinstellungen.

Beim zweiten Überschreiben erstellt ein neues `CDataConnection` Objekt mit den Einstellungen entspricht dem Datenverbindungsobjekt, die Sie angeben.

## <a name="#copy"></a> CDataConnection:: Copy

Erstellt eine Kopie einer vorhandenen Datenverbindung an.

### <a name="syntax"></a>Syntax

```cpp
CDataConnection& Copy(const CDataConnection & ds) throw();
```

#### <a name="parameters"></a>Parameter

*DS*<br/>
[in] Ein Verweis auf eine vorhandene Datenverbindung zu kopieren.

## <a name="#open"></a> CDataConnection:: Open

Öffnet eine Verbindung mit einer Datenquelle mit einer Initialisierungszeichenfolge an.

### <a name="syntax"></a>Syntax

```cpp
HRESULT Open(LPCOLESTR szInitString) throw();
```

#### <a name="parameters"></a>Parameter

*szInitString*<br/>
[in] Die Initialisierungszeichenfolge für die Datenquelle.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

## <a name="#opennewsession"></a> CDataConnection:: Opennewsession

Öffnet eine neue Sitzung mithilfe des aktuellen Verbindungsobjekts-Datenquelle.

### <a name="syntax"></a>Syntax

```cpp
HRESULT OpenNewSession(CSession & session) throw();
```

#### <a name="parameters"></a>Parameter

*Sitzung*<br/>
[in/Out] Ein Verweis auf das Objekt für die neue Sitzung.

### <a name="remarks"></a>Hinweise

Die neue Sitzung des aktuellen Verbindungsobjekts enthaltenen Datenquellenobjekt als übergeordnete Klasse verwendet, und kann auf alle die gleichen Informationen wie die Datenquelle zugreifen.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

## <a name="op_bool"></a> CDataConnection:: Operator BOOL

Bestimmt, ob die aktuelle Sitzung geöffnet oder nicht ist.

### <a name="syntax"></a>Syntax

```cpp
operator BOOL() throw();
```

### <a name="remarks"></a>Hinweise

Gibt **"bool"** (MFC-Typedef)-Wert. **"True"** bedeutet, dass die aktuelle Sitzung geöffnet ist **"False"** bedeutet, dass die aktuelle Sitzung geschlossen wird.

## <a name="op_bool_ole"></a> CDataConnection:: Operator Bool (OLE DB)

Bestimmt, ob die aktuelle Sitzung geöffnet oder nicht ist.

### <a name="syntax"></a>Syntax

```cpp
operator bool() throw();
```

### <a name="remarks"></a>Hinweise

Gibt eine **"bool"** (C++-Datentyp)-Wert. **"true"** bedeutet, dass die aktuelle Sitzung geöffnet ist **"false"** bedeutet, dass die aktuelle Sitzung geschlossen wird.

## <a name="op_cdata_amp"></a> CDataConnection:: Operator CDataSource&amp;

Gibt einen Verweis auf die enthaltene `CDataSource` Objekt.

### <a name="syntax"></a>Syntax

```cpp
operator const CDataSource&() throw();
```

### <a name="remarks"></a>Hinweise

Dieser Operator gibt einen Verweis auf die enthaltene `CDataSource` -Objekt, sodass Sie übergeben eine `CDataConnection` Objekt, in denen eine `CDataSource` Verweis wird erwartet.

### <a name="example"></a>Beispiel

Wenn Sie eine Funktion haben (wie z. B. `func` unten), akzeptiert eine `CDataSource` Verweis können Sie `CDataSource&` übergeben eine `CDataConnection` -Objekt.

[!code-cpp[NVC_OLEDB_Consumer#3](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_1.cpp)]

[!code-cpp[NVC_OLEDB_Consumer#4](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_2.cpp)]

## <a name="op_cdata_star"></a> CDataConnection:: Operator CDataSource *

Gibt einen Zeiger auf die enthaltene `CDataSource` Objekt.

### <a name="syntax"></a>Syntax

```cpp
operator const CDataSource*() throw();
```

### <a name="remarks"></a>Hinweise

Dieser Operator gibt einen Zeiger auf die enthaltene `CDataSource` -Objekt, sodass Sie übergeben eine `CDataConnection` Objekt, in denen eine `CDataSource` Zeiger erwartet wird.

Finden Sie unter [Operator CDataSource &](../../data/oledb/cdataconnection-operator-cdatasource-amp.md) für ein Beispiel zur Verwendung.

## <a name="op_csession_amp"></a> CDataConnection:: Operator CSession&amp;

Gibt einen Verweis auf die enthaltene `CSession` Objekt.

### <a name="syntax"></a>Syntax

```cpp
operator const CSession&();
```

### <a name="remarks"></a>Hinweise

Dieser Operator gibt einen Verweis auf die enthaltene `CSession` -Objekt, sodass Sie übergeben eine `CDataConnection` Objekt, in denen eine `CSession` Verweis wird erwartet.

### <a name="example"></a>Beispiel

Wenn Sie eine Funktion haben (wie z. B. `func` unten), akzeptiert eine `CSession` Verweis können Sie `CSession&` übergeben eine `CDataConnection` -Objekt.

[!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_1.cpp)]

[!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_2.cpp)]

## <a name="op_csession_star"></a> CDataConnection:: Operator CSession *

Gibt einen Zeiger auf die enthaltene `CSession` Objekt.

### <a name="syntax"></a>Syntax

```cpp
operator const CSession*() throw();
```

### <a name="remarks"></a>Hinweise

Dieser Operator gibt einen Zeiger auf die enthaltene `CSession` -Objekt, sodass Sie übergeben eine `CDataConnection` Objekt, in denen eine `CSession` Zeiger erwartet wird.

### <a name="example"></a>Beispiel

Finden Sie unter [Operator-CSession &](../../data/oledb/cdataconnection-operator-csession-amp.md) für ein Beispiel zur Verwendung.

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)