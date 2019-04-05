---
title: Benutzerdatensatz
ms.date: 11/04/2016
helpviewer_keywords:
- records, user
- OLE DB providers, user record
- user records
- user records, described
- rowsets, user record
ms.assetid: 9c0d2864-2738-4f62-a750-1016d9c3523f
ms.openlocfilehash: b37835f1a3161edd10f61f9b4e76cfb5f558e07b
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038517"
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
