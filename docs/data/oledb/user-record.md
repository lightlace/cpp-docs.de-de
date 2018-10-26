---
title: Benutzerdatensatz | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- records, user
- OLE DB providers, user record
- user records
- user records, described
- rowsets, user record
ms.assetid: 9c0d2864-2738-4f62-a750-1016d9c3523f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1c1958604edbb2f9d9c10e58082e70c2df400b8c
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50077373"
---
# <a name="user-record"></a>Benutzerdatensatz

Der Benutzerdatensatz enthält den Code und Daten-Struktur, die die Spaltendaten für ein Rowset darstellt. Ein Benutzerdatensatz kann zum Zeitpunkt der Kompilierung oder zur Laufzeit erstellt werden. Wenn Sie einen Anbieter mithilfe der ATL-OLE DB-Anbieter-Assistenten erstellen, wird der Assistent erstellt ein Standard-Benutzer-Eintrag, der folgendermaßen aussieht (vorausgesetzt, einen Anbieternamen [kurzer Name] des angegebenen *benutzerdefinierte*):

```cpp
class CWindowsFile:
   public WIN32_FIND_DATA
{
public:

BEGIN_PROVIDER_COLUMN_MAP(CCustomWindowsFile)
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)
END_PROVIDER_COLUMN_MAP()

};
```

Der OLE DB-Anbietervorlagen behandeln alle OLE DB-Besonderheiten in Bezug auf die Interaktionen mit dem Client. Um der Spaltendaten benötigt wird, auf eine Antwort zu erhalten, der Anbieter Ruft die `GetColumnInfo` -Funktion, die Sie in der Benutzerdatensatz einfügen müssen. Sie können explizit überschreiben `GetColumnInfo` im Benutzerdatensatz, z. B. durch Deklarieren sie in der h-Datei wie hier gezeigt:

```cpp
template <class T>
static ATLCOLUMNINFO* GetColumnInfo(T* pThis, ULONG* pcCols)
```

Das entspricht:

```cpp
static ATLCOLUMNINFO* GetColumnInfo(CommandClass* pThis, ULONG* pcCols)
static ATLCOLUMNINFO* GetColumnInfo(RowsetClass* pThis, ULONG* pcCols)
```

Sie müssen auch implementieren `GetColumnInfo` in der Benutzerdatensatz cpp-Datei.

Die Makro-Makros, bei der Erstellung einer `GetColumnInfo` Funktion:

- BEGIN_PROVIDER_COLUMN_MAP definiert, der Funktionsprototyp und einen statischen Array von `ATLCOLUMNINFO` Strukturen.

- Durch definiert und initialisiert ein einzelnes `ATLCOLUMNINFO`.

- END_PROVIDER_COLUMN_MAP schließt das Array und die Funktion. Es wird auch die Anzahl der Arrayelemente in das *PcCols* Parameter.

Wenn ein Benutzerdatensatz, zur Laufzeit erstellt wird `GetColumnInfo` verwendet die *pThis* Parameter, um einen Zeiger auf eine Instanz von Rowset- oder erhalten. Befehle und Rowsets unterstützen, muss die `IColumnsInfo` Schnittstelle, damit die Spalteninformationen aus diesem Zeiger abgerufen werden kann.

`CommandClass` und `RowsetClass` entsprechen dem Befehl und das Rowset, das den Benutzerdatensatz zu verwenden.

Ein ausführlicheres Beispiel zum Überschreiben `GetColumnInfo` in einem Benutzerdatensatz finden Sie unter [Dynamisches Festlegen der an den Consumer zurückgegebenen Spalten](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).

## <a name="see-also"></a>Siehe auch

[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)