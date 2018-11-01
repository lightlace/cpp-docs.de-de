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
ms.openlocfilehash: e37ed0ac918b004513aa64308870a534a7b2af40
ms.sourcegitcommit: 840033ddcfab51543072604ccd5656fc6d4a5d3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "50216291"
---
# <a name="user-record"></a>Benutzerdatensatz

Der Benutzerdatensatz enthält den Code und Daten-Struktur, die die Spaltendaten für ein Rowset darstellt. Ein Benutzerdatensatz kann zum Zeitpunkt der Kompilierung oder zur Laufzeit erstellt werden. Beim Erstellen eines Anbieters mithilfe der **ATL-OLE DB-Anbieter-Assistenten**, erstellt der Assistent ein Standard-Benutzer-Eintrag, der folgendermaßen aussieht (vorausgesetzt, einen Anbieternamen [kurzer Name] des angegebenen *MyProvider*):

```cpp
class CWindowsFile:
   public WIN32_FIND_DATA
{
public:
  
BEGIN_PROVIDER_COLUMN_MAP(CMyProviderWindowsFile)
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)
END_PROVIDER_COLUMN_MAP()
  
};
```

Der OLE DB-Anbietervorlagen behandeln alle OLE DB-Angaben darüber, Interaktionen mit dem Client. Um der Spaltendaten benötigt wird, auf eine Antwort zu erhalten, der Anbieter Ruft die `GetColumnInfo` -Funktion, die Sie in der Benutzerdatensatz einfügen müssen. Sie können explizit überschreiben `GetColumnInfo` im Benutzerdatensatz, z. B. durch Deklarieren sie in der h-Datei wie hier gezeigt:

```cpp
template <class T>
static ATLCOLUMNINFO* GetColumnInfo(T* pThis, ULONG* pcCols) 
```

Dies entspricht:

```cpp
static ATLCOLUMNINFO* GetColumnInfo(CommandClass* pThis, ULONG* pcCols)
static ATLCOLUMNINFO* GetColumnInfo(RowsetClass* pThis, ULONG* pcCols)
```

Implementieren Sie anschließend die `GetColumnInfo` in der Benutzerdatensatz cpp-Datei.

Die Makro-Makros, bei der Erstellung einer `GetColumnInfo` Funktion:

- BEGIN_PROVIDER_COLUMN_MAP definiert, der Funktionsprototyp und einen statischen Array von `ATLCOLUMNINFO` Strukturen.

- Durch definiert und initialisiert ein einzelnes `ATLCOLUMNINFO`.

- END_PROVIDER_COLUMN_MAP schließt das Array und die Funktion. Es wird auch die Anzahl der Arrayelemente in das *PcCols* Parameter.

Wenn ein Benutzerdatensatz, zur Laufzeit erstellt wird `GetColumnInfo` verwendet die *pThis* Parameter, um einen Zeiger auf eine Instanz von Rowset- oder erhalten. Befehle und Rowsets unterstützen, muss die `IColumnsInfo` Schnittstelle, damit die Spalteninformationen aus diesem Zeiger entnommen werden kann.

`CommandClass` und `RowsetClass` entsprechen dem Befehl und das Rowset, das den Benutzerdatensatz zu verwenden.

Ein ausführlicheres Beispiel zum Überschreiben `GetColumnInfo` in einem Benutzerdatensatz finden Sie unter [Dynamisches Festlegen der an den Consumer zurückgegebenen Spalten](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).

## <a name="see-also"></a>Siehe auch

[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
