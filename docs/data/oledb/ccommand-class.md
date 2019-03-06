---
title: CCommand-Klasse
ms.date: 11/04/2016
f1_keywords:
- ATL::CCommand
- CCommand
- ATL.CCommand
- CCommand.Close
- CCommand::Close
- CCommand.Create
- CCommand::Create
- CCommand.CreateCommand
- CreateCommand
- CCommand::CreateCommand
- ATL::CCommand::GetNextResult
- CCommand::GetNextResult
- GetNextResult
- CCommand.GetNextResult
- ATL.CCommand.GetNextResult
- GetParameterInfo
- CCommand.GetParameterInfo
- CCommand::GetParameterInfo
- ATL.CCommand.Open
- ATL::CCommand::Open
- CCommand.Open
- CCommand::Open
- CCommand.Prepare
- CCommand::Prepare
- Prepare
- CCommand.ReleaseCommand
- ReleaseCommand
- CCommand::ReleaseCommand
- SetParameterInfo
- CCommand.SetParameterInfo
- CCommand::SetParameterInfo
- Unprepare
- CCommand.Unprepare
- CCommand::Unprepare
helpviewer_keywords:
- CCommand class
- Close method
- Create method [C++]
- CreateCommand method
- GetNextResult method
- GetParameterInfo method
- Open method
- Prepare method
- ReleaseCommand method
- SetParameterInfo method
- Unprepare method
ms.assetid: 0760bfc5-b9ee-4aee-8e54-31bd78714d3a
ms.openlocfilehash: 7db2d3d71deecda06e39772541658dfada72ae3b
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57415265"
---
# <a name="ccommand-class"></a>CCommand-Klasse

Stellt Methoden zum Festlegen und einen Befehl ausführen.

## <a name="syntax"></a>Syntax

```cpp
template <class TAccessor = CNoAccessor,
   template <typename T> class TRowset = CRowset,
   class TMultiple = CNoMultipleResults>
class CCommand :
   public CAccessorRowset <TAccessor, TRowset>,
   public CCommandBase,
   public TMultiple
```

### <a name="parameters"></a>Parameter

*TAccessor*<br/>
Der Typ der Accessorklasse (z. B. `CDynamicParameterAccessor`, `CDynamicStringAccessor`, oder `CEnumeratorAccessor`), dass der Befehl verwendet werden sollen. Der Standardwert ist `CNoAccessor`, der angibt, dass die Klasse nicht unterstützen Parameter oder Spalten ausgeben.

*TRowset*<br/>
Der Typ der Rowsetklasse (z. B. `CArrayRowset` oder `CNoRowset`), dass der Befehl verwendet werden sollen. Die Standardeinstellung ist `CRowset`.

*TMultiple*<br/>
Um einen OLE DB-Befehl verwenden, die mehrere Ergebnisse zurückgegeben werden können, geben [CMultipleResults](../../data/oledb/cmultipleresults-class.md). Verwenden Sie andernfalls [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md). Weitere Informationen finden Sie unter [IMultipleResults](/previous-versions/windows/desktop/ms721289(v=vs.85)).

## <a name="requirements"></a>Anforderungen

**Header:** atldbcli.h

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[Schließen](#close)|Schließt den aktuellen Befehl.|
|[GetNextResult](#getnextresult)|Ruft das nächste Ergebnis beim Verwenden von mehreren Resultsets ab.|
|[Öffnen](#open)|Wird ausgeführt, und bindet optional den Befehl.|

### <a name="inherited-methods"></a>Geerbte Methoden

|||
|-|-|
|[Erstellen](#create)|Erstellt einen neuen Befehl für die angegebene Sitzung, und legt dann den Befehlstext.|
|[CreateCommand](#createcommand)|Erstellt einen neuen Befehl.|
|[GetParameterInfo](#getparameterinfo)|Ruft eine Liste von die Befehls Parameter, deren Namen und ihre Typen ab.|
|[Vorbereiten](#prepare)|Überprüft, und den aktuellen Befehl optimiert.|
|[ReleaseCommand](#releasecommand)|Bei Bedarf den Parameteraccessor frei, und dann den Befehl frei.|
|[SetParameterInfo](#setparameterinfo)|Gibt den systemeigenen Typ für jeden Befehlsparameter.|
|[Unprepare](#unprepare)|Verwirft den aktuellen Befehl Ausführungsplan.|

## <a name="remarks"></a>Hinweise

Verwenden Sie diese Klasse, wenn Sie verwenden möchten, führen Sie einen Parametern basierenden Vorgang oder einen Befehl auszuführen. Wenn Sie nur ein einfaches Rowsets öffnen müssen, verwenden Sie [CTable](../../data/oledb/ctable-class.md) stattdessen.

Der Accessorklasse, die Sie verwenden bestimmt die Methode der Bindung von Parametern und Daten.

Beachten Sie, dass Sie gespeicherte Prozeduren mit dem OLE DB-Anbieter für Jet verwenden nicht möglich, da dieser Anbieter nicht unterstützt gespeicherte Prozeduren, die (nur Konstanten sind in Abfragezeichenfolgen zulässig).

## <a name="close"></a> CCommand:: Close

Gibt die Accessor-Rowset, das dem Befehl zugeordnet.

### <a name="syntax"></a>Syntax

```cpp
void Close();
```

### <a name="remarks"></a>Hinweise

Ein Befehl verwendet ein Rowset, Ergebnis Set-Accessor und (optional) Parameteraccessor (im Gegensatz zu Tabellen, die Parameter nicht unterstützt und ist nicht erforderlich, einen).

Wenn Sie einen Befehl ausführen, sollten Sie beide Aufrufen `Close` und [ReleaseCommand](../../data/oledb/ccommand-releasecommand.md) nach dem Befehl.

Wenn Sie denselben Befehl wiederholt ausführen möchten, sollten Sie jedes Ergebnis Set-Accessor freigeben, durch Aufrufen von `Close` vor dem Aufruf `Execute`. Am Ende der Reihe, sollten Sie die Parameteraccessor freigeben, indem er `ReleaseCommand`. Ein weiteres gängiges Szenario ist das Aufrufen einer gespeicherten Prozedur, die Output-Parameter aufweist. In vielen Anbietern (z. B. der OLE DB-Anbieter für SQL Server) werden die Werte der Ausgabeparameter nicht zugegriffen werden, bis zum Schließen des Ergebnis-Set-Accessors. Rufen Sie `Close` zum Schließen des zurückgegebenen Rowsets und Ergebnis-Set-Accessor, jedoch nicht den Parameteraccessor ermöglicht daher die Werte der Ausgabeparameter abzurufen.

### <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie aufrufen können `Close` und `ReleaseCommand` Wenn Sie den gleichen Befehl wiederholt ausführen.

[!code-cpp[NVC_OLEDB_Consumer#2](../../data/oledb/codesnippet/cpp/ccommand-close_1.cpp)]

## <a name="getnextresult"></a> CCommand::GetNextResult

Ruft das nächste Resultset, sofern verfügbar.

### <a name="syntax"></a>Syntax

```cpp
HRESULT GetNextResult(DBROWCOUNT* pulRowsAffected,
   bool bBind = true) throw();
```

#### <a name="parameters"></a>Parameter

*pulRowsAffected*<br/>
[in/Out] Ein Zeiger auf den Speicher, in dem die Anzahl der von einem Befehl betroffenen Zeilen zurückgegeben wird.

*bBind*<br/>
[in] Gibt an, ob den Befehl bindet automatisch nach dem ausgeführt wird. Der Standardwert ist **"true"**, die bewirkt, dass der Befehl automatisch gebunden werden. Festlegen von *bBind* zu **"false"** wird verhindert, dass die automatische Bindung des Befehls, sodass Sie manuell binden können. (Manuelle Bindung ist von besonderem Interesse für OLAP-Benutzer.)

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

### <a name="remarks"></a>Hinweise

Wenn zuvor ein Resultset abgerufen wurde, wird diese Funktion das vorherige Resultset frei und hebt die Bindung der Spalten. Wenn *bBind* ist **"true"**, es wird an die neuen Spalten gebunden.

Sie sollten diese Funktion aufrufen, nur dann, wenn Sie mehrere Ergebnisse, durch Festlegen angegeben haben der `CCommand` Vorlagenparameter *TMultiple*=`CMultipleResults`.

## <a name="open"></a> CCommand:: Open

Wird ausgeführt, und bindet optional den Befehl.

### <a name="syntax"></a>Syntax

```cpp
HRESULT Open(const CSession& session,
   LPCWSTR wszCommand,
   DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   REFGUID guidCommand = DBGUID_DEFAULT,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();

HRESULT Open(const CSession& session,
   LPCSTR szCommand,
   DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   REFGUID guidCommand = DBGUID_DEFAULT,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();

HRESULT Open(const CSession& session,
   INT szCommand = NULL,
   DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   REFGUID guidCommand = DBGUID_DEFAULT,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();

HRESULT Open(DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();
```

#### <a name="parameters"></a>Parameter

*session*<br/>
[in] Die Sitzung, in dem den Befehl ausgeführt werden soll.

*wszCommand*<br/>
[in] Der Befehl ausgeführt werden, werden als Unicode-Zeichenfolge übergeben. Kann NULL sein, wenn mit `CAccessor`, in diesem Fall der Befehl aus den übergebenen Wert abgerufen werden die [DEFINE_COMMAND](../../data/oledb/define-command.md) Makro. Finden Sie unter [ICommand:: Execute](/previous-versions/windows/desktop/ms718095(v=vs.85)) in die *OLE DB-Programmierreferenz* Details.

*szCommand*<br/>
[in] Identisch mit *WszCommand* außer dass dieser Parameter eine Zeichenfolge der ANSI-Befehl verwendet. Die vierte Form von dieser Methode dauert einen NULL-Wert. Finden Sie unter "Hinweise" weiter unten in diesem Thema finden Sie Details ein.

*pPropSet*<br/>
[in] Ein Zeiger auf ein Array von [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) Strukturen, die Eigenschaften und Werte festgelegt werden. Finden Sie unter [Eigenschaftensätze und Eigenschaftengruppen](/previous-versions/windows/desktop/ms713696(v=vs.85)) in die *OLE DB-Programmierreferenz* in das Windows SDK.

*pRowsAffected*<br/>
[in/Out] Ein Zeiger auf den Speicher, in dem die Anzahl der von einem Befehl betroffenen Zeilen zurückgegeben wird. Wenn  *\*pRowsAffected* NULL ist, keine Zeilenanzahl zurückgegeben wird. Andernfalls `Open` legt  *\*pRowsAffected* gemäß den folgenden Bedingungen:

|If|Then|
|--------|----------|
|Die `cParamSets` Element `pParams` ist größer als 1|*\*pRowsAffected* stellt die Gesamtzahl der Zeilen, die von allen von der der Ausführung angegebenen Parametersätzen betroffen sind.|
|Die Anzahl der betroffenen Zeilen ist nicht verfügbar|*\*pRowsAffected* wird auf-1 festgelegt.|
|Der Befehl wird nicht aktualisiert werden, löschen oder Einfügen von Zeilen|*\*pRowsAffected* ist nicht definiert.|

*guidCommand*<br/>
[in] Eine GUID, die Syntax und die allgemeinen Regeln für den zu verwendenden Anbieter angibt, bei der Analyse des Befehlstexts. Finden Sie unter [ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85)) und [ICommandText:: SetCommandText](/previous-versions/windows/desktop/ms709757(v=vs.85)) in die *OLE DB-Programmierreferenz* Details.

*bBind*<br/>
[in] Gibt an, ob den Befehl bindet automatisch nach dem ausgeführt wird. Der Standardwert ist **"true"**, die bewirkt, dass der Befehl automatisch gebunden werden. Festlegen von *bBind* zu **"false"** wird verhindert, dass die automatische Bindung des Befehls, sodass Sie manuell binden können. (Manuelle Bindung ist von besonderem Interesse für OLAP-Benutzer.)

*ulPropSets*<br/>
[in] Die Anzahl der [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) Strukturen zu übergeben, der *DBPROPSET* Argument.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

### <a name="remarks"></a>Hinweise

Die ersten drei Formen von `Open` eine Sitzung nutzen, erstellen Sie einen Befehl und führen Sie den Befehl, binden alle Parameter nach Bedarf.

Die erste Form der `Open` eine Zeichenkette Unicode-Befehl aus, und hat keinen Standardwert.

Die zweite Form der `Open` nimmt eine ANSI-Befehl-Zeichenfolge und kein Standardwert (für Abwärtskompatibilität mit vorhandenen ANSI-Anwendungen bereitgestellt).

Die dritte Form der `Open` können Sie die Befehlszeichenfolge gleich NULL ist, aufgrund der Art **Int** hat den Standardwert NULL. Er wird bereitgestellt, für den Aufruf `Open(session, NULL);` oder `Open(session);` weil NULL vom Typ **Int**. Diese Version ist erforderlich und Assert-Vorgänge, die die **Int** Parameter NULL sein.

Verwenden Sie die vierte Form der `Open` Wenn Sie einen Befehl bereits erstellt haben, und Sie eine einzelnen auszuführenden [vorbereiten](../../data/oledb/ccommand-prepare.md) und mehrere Ausführungen.

> [!NOTE]
>  `Open` Aufrufe `Execute`, die wiederum ruft `GetNextResult`.

## <a name="create"></a> CCommand:: Create

Aufrufe [CCommand:: CreateCommand](../../data/oledb/ccommand-createcommand.md) erstellen Sie einen Befehl für die angegebene Sitzung, ruft dann [ICommandText:: SetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85)) der Befehlstext an.

### <a name="syntax"></a>Syntax

```cpp
HRESULT CCommandBase::Create(const CSession& session,
   LPCWSTR wszCommand,
   REFGUID guidCommand = DBGUID_DEFAULT) throw ();

HRESULT CCommandBase::Create(const CSession& session,
   LPCSTR szCommand,
   REFGUID guidCommand = DBGUID_DEFAULT) throw ();
```

#### <a name="parameters"></a>Parameter

*session*<br/>
[in] Eine Sitzung auf dem den Befehl erstellt werden soll.

*wszCommand*<br/>
[in] Ein Zeiger auf den Unicode-Text, der die Befehlszeichenfolge.

*szCommand*<br/>
[in] Ein Zeiger auf das ANSI-Text der Befehlszeichenfolge.

*guidCommand*<br/>
[in] Eine GUID, die Syntax und die allgemeinen Regeln für den zu verwendenden Anbieter angibt, bei der Analyse des Befehlstexts. Eine Beschreibung der Dialekte, finden Sie unter [ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85)) in die *OLE DB-Programmierreferenz*.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

### <a name="remarks"></a>Hinweise

Die erste Form der `Create` eine Zeichenkette Unicode-Befehl. Die zweite Form der `Create` nimmt eine ANSI-Befehl-Zeichenfolge (für Abwärtskompatibilität mit vorhandenen ANSI-Anwendungen bereitgestellt).

## <a name="createcommand"></a> CCommand::CreateCommand

Erstellt einen neuen Befehl.

### <a name="syntax"></a>Syntax

```cpp
HRESULT CCommandBase::CreateCommand(const CSession& session) throw ();
```

#### <a name="parameters"></a>Parameter

*session*<br/>
[in] Ein `CSession` Objekt, das den neuen Befehl zugeordnet werden.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

### <a name="remarks"></a>Hinweise

Diese Methode erstellt einen Befehl unter Verwendung des angegebenen Objekts.

## <a name="getparameterinfo"></a> CCommand::GetParameterInfo

Ruft eine Liste von die Befehls Parameter, deren Namen und ihre Typen ab.

### <a name="syntax"></a>Syntax

```cpp
HRESULT CCommandBase::GetParameterInfo(DB_UPARAMS* pParams,
   DBPARAMINFO** ppParamInfo,
   OLECHAR** ppNamesBuffer) throw ();
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [ICommandWithParameters:: GetParameterInfo](/previous-versions/windows/desktop/ms714917(v=vs.85)) in die *OLE DB-Programmierreferenz*.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

## <a name="prepare"></a> CCommand:: Prepare

Überprüft, und den aktuellen Befehl optimiert.

### <a name="syntax"></a>Syntax

```cpp
HRESULT CCommandBase::Prepare(ULONG cExpectedRuns = 0) throw();
```

#### <a name="parameters"></a>Parameter

*cExpectedRuns*<br/>
[in] Die Anzahl der Male, die Sie erwarten, beim Ausführen des Befehls dass.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

### <a name="remarks"></a>Hinweise

Diese Methode dient als Wrapper für OLE DB-Methode [ICommandPrepare:: Prepare](/previous-versions/windows/desktop/ms718370(v=vs.85)).

## <a name="releasecommand"></a> CCommand:: ReleaseCommand

Den Parameteraccessor frei, und den Befehl selbst frei.

### <a name="syntax"></a>Syntax

```cpp
void CCommandBase::ReleaseCommand() throw();
```

### <a name="remarks"></a>Hinweise

`ReleaseCommand` wird verwendet, in Verbindung mit `Close`. Finden Sie unter [schließen](../../data/oledb/ccommand-close.md) zur Verwendung.

## <a name="setparameterinfo"></a> CCommand::SetParameterInfo

Gibt den systemeigenen Typ für jeden Befehlsparameter.

### <a name="syntax"></a>Syntax

```cpp
HRESULT CCommandBase::SetParameterInfo(DB_UPARAMS ulParams,
   const DBORDINAL* pOrdinals,
   const DBPARAMBINDINFO* pParamInfo) throw();
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [ICommandWithParameters:: SetParameterInfo](/previous-versions/windows/desktop/ms725393(v=vs.85)) in die *OLE DB-Programmierreferenz*.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

## <a name="unprepare"></a> CCommand:: Unprepare

Verwirft den aktuellen Befehl Ausführungsplan.

### <a name="syntax"></a>Syntax

```cpp
HRESULT CCommandBase::Unprepare() throw();
```

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

### <a name="remarks"></a>Hinweise

Diese Methode dient als Wrapper für OLE DB-Methode [ICommandPrepare:: Unprepare](/previous-versions/windows/desktop/ms719635(v=vs.85)).

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)