---
title: Db_command | Microsoft-Dokumentation
ms.custom: ''
ms.date: 07/10/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_command
dev_langs:
- C++
helpviewer_keywords:
- db_command attribute
ms.assetid: 714c3e15-85d7-408b-9a7c-88505c3e5d24
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6140b6764efe530664a1904940f3a8426e6fee02
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46445855"
---
# <a name="dbcommand"></a>db_command

Erstellt einen OLE DB-Befehl.

## <a name="syntax"></a>Syntax

```cpp
[ db_command(
   command,
   name,
   source_name,
   hresult,
   bindings,
   bulk_fetch)  
]
```

### <a name="parameters"></a>Parameter

*command*<br/>
Eine Befehlszeichenfolge, die den Text eines OLE DB-Befehls enthält. Ein einfaches Beispiel lautet:

```cpp
[ db_command ( command = "Select * from Products" ) ]
```

Die *Befehlssyntax* lautet wie folgt:

> Binding Parameterblock 1 &nbsp; &nbsp;OLE DB-Befehl Binding Parameterblock 2 &nbsp; &nbsp;Fortsetzung des OLE DB-Befehl Binding Parameterblock 3...

*binding parameter block* ist folgendermaßen definiert:

> **(\[**  *Bindtype* **]** *szVar1* \[, *szVar2* \[, *nVar3* \[,...]]] **)**

Dabei gilt:

- **(** kennzeichnet den Anfang des Datenbindungsblocks.

- **\[** *BindType* **]** ist eine der folgenden Zeichenfolgen, Groß-/Kleinschreibung:

  - **\[Db_column]** bindet die einzelnen Membervariablen an eine Spalte in einem Rowset.

  - **\[BindTo]** (identisch mit  **\[Db_column]**).

  - **\[in]** bindet Membervariablen als Eingabeparameter.

  - **\[Out]** bindet Membervariablen als Ausgabeparameter.

  - **\[in, Out]** bindet Membervariablen als ein-/Ausgabeparameter.

- *SzVarX*, *nVarX* wird in einer Membervariablen im aktuellen Gültigkeitsbereich aufgelöst.

- **)** kennzeichnet das Ende des Datenbindungsblocks.

Wenn die Befehlszeichenfolge einen oder mehrere Bezeichner, z. B. enthält \[im], \[out], oder \[in/out], **Db_command** eine parameterzuordnung.

Wenn die Befehlszeichenfolge einen oder mehrere Parameter, z. B. enthält \[Db_column] oder \[Bindto], **Db_command** generiert wird, ein Rowset und eine accessorkarte, um diese gebundenen Variablen zu bedienen. Weitere Informationen finden Sie unter [db_accessor](../windows/db-accessor.md) .

> [!NOTE]
> \[*BindType*] Syntax und die *Bindungen* Parameter sind nicht gültig, wenn **Db_command** auf Klassenebene.

Nachfolgend finden Sie einige Beispiele für „binding parameter block“. Im folgenden Beispiel werden die Datenmember `m_au_fname` und `m_au_lname` jeweils an die Spalten `au_fname` und `au_lname` der Autorentabelle in der pubs-Datenbank gebunden:

```cpp
TCHAR m_au_fname[21];
TCHAR m_au_lname[41];
TCHAR m_state[3] = 'CA';

[db_command (
   command = "SELECT au_fname([bindto]m_au_fname), au_lname([bindto]m_au_lname) " \
   "FROM dbo.authors " \
   "WHERE state = ?([in]m_state)")  
]
```

*name*<br/>
(Optional) Der Name des Handles, die Sie verwenden, um die Arbeit mit dem Rowset. Wenn Sie *name*angeben, generiert **db_command** eine Klasse mit dem angegebenen *Namen*, das verwendet werden kann, um das Rowset zu traversieren oder mehrere Aktionsabfragen auszuführen. Wenn Sie *name*nicht angeben, ist es nicht möglich, mehr als eine Zeile mit Ergebnissen an den Benutzer zurückzugeben.

*source_name*<br/>
(Optional) Die `CSession` Variable oder eine Instanz einer Klasse, die die `db_source` -Attribut angewendet, auf dem der Befehl ausgeführt wird. Informationen hierzu finden Sie unter [db_source](../windows/db-source.md).

**db_command** stellt sicher, dass die Variable für *source_name* gültig ist, um den Gültigkeitsbereich der angegebenen Variablen auf eine Funktion oder als global festzulegen.

*HRESULT*<br/>
(Optional) Identifiziert die Variable, die das HRESULT des diesem Datenbankbefehl erhält. Wenn die Variable nicht existiert, wird sie automatisch durch das Attribut eingefügt.

*bindings*<br/>
(Optional) Ermöglicht Ihnen die Bindungsparameter vom OLE DB-Befehl zu trennen.

Bei Angabe ein Werts für *Bindungen*, **Db_command** analysiert den zugeordneten Wert und nicht die \[ *Bindtype*] Parameter. Dies ermöglicht Ihnen die Verwendung der OLE DB-Anbietersyntax. Geben Sie zum Deaktivieren der Analyse ohne Bindungsparameter `Bindings=""`.

Wenn Sie einen Wert für nicht angeben *Bindungen*, **Db_command** analysiert Bindung Parameterblock, Suche nach "**(**", gefolgt von **\[** _Bindtype_**]** in Klammern, gefolgt von einem oder mehreren zuvor deklarierten C++-Membervariablen, gefolgt von "**)**". Der in Klammern gefasste Text wird aus dem sich ergebenden Befehl entfernt, und diese Parameter werden verwendet, um die Spalten- und Parameterbindungen für diesen Befehl zu erstellen.

*bulk_fetch*<br/>
(Optional) Ein ganzzahliger Wert, der die Anzahl der abzurufenden Zeilen angibt.

Mit dem Standardwert 1 werden die Zeilen einzeln abgerufen (das Rowset ist vom Typ [CRowset](../data/oledb/crowset-class.md)).

Ein höherer Wert als 1 gibt das Massenabrufen von Zeilen an. Das Massenabrufen von Zeilen bezieht sich auf die Fähigkeit von Massenrowsets, mehrere Zeilenhandles abzurufen (das Rowset ist vom Typ [CBulkRowset](../data/oledb/cbulkrowset-class.md) und wird `SetRows` mit der angegebenen Anzahl von Zeilen aufrufen).

Wenn *bulk_fetch* kleiner als 1 ist, gibt `SetRows` 0 (Null) zurück.

## <a name="remarks"></a>Hinweise

**db_command** erstellt ein [CCommand](../data/oledb/ccommand-class.md) -Objekt, das von einem OLE DB-Consumer verwendet wird, um einen Befehl auszuführen.

Sie können **db_command** entweder mit einem Klassen- oder Funktionsbereich verwenden. Der Hauptunterschied liegt im Bereich des `CCommand` -Objekts. Ist der Gültigkeitsbereich auf die Funktion beschränkt, werden Daten wie z.B. Bindungen bei Beendigung der Funktion ebenfalls beendet. Sowohl die Klasse als auch die Funktion Bereich Verwendungen umfassen die Klasse des OLE DB-Consumervorlagen `CCommand<>`, unterscheiden sich die Vorlagenargumente für die Fälle Funktion und der Klasse. Des Funktionsbereichs Bindungen werden versucht, eine `Accessor` , enthält lokale Variablen, erfordert, während die Verwendung der-Klasse ableitet, eine `CAccessor`-abgeleitete Klasse als Argument. Wenn es als Klassenattribut verwendet wird, funktioniert **db_command** zusammen mit **db_column**.

Mit**db_command** können Befehle ausgeführt werden, die kein Resultset zurückgeben.

Wenn der Consumer Attributanbieter dieses Attribut auf eine Klasse angewendet wird, wird der Compiler die Klasse umbenennen \_ *Klassenname*Accessor, in denen *Klassenname* ist der Name, der Sie zugewiesen haben die Klasse und der Compiler erstellt auch eine Klasse namens *Klassenname*, die sich daraus ableitet \_ *Klassenname*Accessor.  In dieser Klassenansicht werden beide Klassen angezeigt.

## <a name="example"></a>Beispiel

In diesem Beispiel wird ein Befehl definiert, der die Vor- und Nachnamen aus einer Tabelle auswählt, in der die Statusspalte „CA“ entspricht. **db_command** erstellt und liest ein Rowset, für das Sie sowohl über den Assistenten generierte Funktionen wie [OpenAll und CloseAll](../data/oledb/consumer-wizard-generated-methods.md)als auch `CRowset` -Memberfunktionen wie [MoveNext](../data/oledb/crowset-movenext.md)ausführen können.

Beachten Sie, dass Sie für diesen Code eine eigene Verbindungszeichenfolge bereitstellen müssen, die eine Verbindung mit der pubs-Datenbank herstellt. Weitere Informationen dazu in der Entwicklungsumgebung, finden Sie unter [Vorgehensweise: Verbinden mit einer Datenbank und Durchsuchen vorhandener Objekte](/sql/ssdt/how-to-connect-to-a-database-and-browse-existing-objects) und [neue Verbindungen hinzufügen](/visualstudio/data-tools/add-new-connections).

```cpp
// db_command.h
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

#pragma once

[  db_source(L"your connection string"),
   db_command(L" \
      SELECT au_lname, au_fname \
      FROM dbo.authors \
      WHERE state = 'CA'")  ]

struct CAuthors {
   // In order to fix several issues with some providers, the code below may bind
   // columns in a different order than reported by the provider

   DBSTATUS m_dwau_lnameStatus;
   DBSTATUS m_dwau_fnameStatus;
   DBLENGTH m_dwau_lnameLength;
   DBLENGTH m_dwau_fnameLength;

   [ db_column("au_lname", status="m_dwau_lnameStatus", length="m_dwau_lnameLength") ] TCHAR m_au_lname[41];
   [ db_column("au_fname", status="m_dwau_fnameStatus", length="m_dwau_fnameLength") ] TCHAR m_au_fname[21];

   [ db_param("7", paramtype="DBPARAMIO_INPUT") ] TCHAR m_state[3];

   void GetRowsetProperties(CDBPropSet* pPropSet) {
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
   }
};
```

## <a name="example"></a>Beispiel

```cpp
// db_command.cpp
// compile with: /c
#include "db_command.h"

int main(int argc, _TCHAR* argv[]) {
   HRESULT hr = CoInitialize(NULL);

   // Instantiate rowset
   CAuthors rs;

   // Open rowset and move to first row
   strcpy_s(rs.m_state, sizeof(rs.m_state), _T("CA"));
   hr = rs.OpenAll();
   hr = rs.MoveFirst();

   // Iterate through the rowset
   while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET ) {
      // Print out the column information for each row
      printf("First Name: %s, Last Name: %s\n", rs.m_au_fname, rs.m_au_lname);
      hr = rs.MoveNext();
   }

   rs.CloseAll();
   CoUninitialize();
}
```

## <a name="example"></a>Beispiel

In diesem Beispiel wird `db_source` auf die Datenquellenklasse `CMySource`angewendet und `db_command` auf die Befehlsklassen `CCommand1` und `CCommand2`.

```cpp
// db_command_2.cpp
// compile with: /c
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>
// class usage for both db_source and db_command

[  db_source(L"your connection string"),
   db_command(L" \
      SELECT au_lname, au_fname \
      FROM dbo.authors \
      WHERE state = 'CA'")  ]
struct CMySource {
   HRESULT OpenDataSource() {
      return S_OK;
   }
};

[db_command(command = "SELECT * FROM Products")]
class CCommand1 {};

[db_command(command = "SELECT FNAME, LNAME FROM Customers")]
class CCommand2 {};

int main() {
   CMySource s;
   HRESULT hr = s.OpenDataSource();
   if (SUCCEEDED(hr)) {
      CCommand1 c1;
      hr = c1.Open(s);

      CCommand2 c2;
      hr = c2.Open(s);
   }

   s.CloseDataSource();
}
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**, Member, Methode, lokal|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumerattribute](../windows/ole-db-consumer-attributes.md)<br/>
[Eigenständige Attribute](../windows/stand-alone-attributes.md)  
