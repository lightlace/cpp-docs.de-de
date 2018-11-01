---
title: CCustomWindowsFile
ms.date: 10/22/2018
f1_keywords:
- cmyproviderwindowsfile
- ccustomwindowsfile
helpviewer_keywords:
- CMyProviderWindowsFile class
- OLE DB providers, wizard-generated files
- CCustomWindowsFile class
ms.assetid: 0e9e72ac-1e1e-445f-a7ac-690c20031f9d
ms.openlocfilehash: 008fe318ee96248dfca0c3c87bf660726beb3092
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660825"
---
# <a name="ccustomwindowsfile"></a>CCustomWindowsFile

Der Assistent erstellt eine Klasse, die eine Zeile mit Daten verfügt. In diesem Fall heißt es `CCustomWindowsFile`. Der folgende code für `CCustomWindowsFile` Assistenten generiert wird, und listet alle Dateien in einem Verzeichnis mit dem `WIN32_FIND_DATA` Struktur. `CCustomWindowsFile` erbt von der `WIN32_FIND_DATA` Struktur:

```cpp
/////////////////////////////////////////////////////////////////////
// CustomRS.H

class CCustomWindowsFile: 
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

`CCustomWindowsFile` wird aufgerufen, die [Benutzerdatensatz-Klasse](../../data/oledb/user-record.md) , da sie hat auch eine Zuordnung, die Beschreibung der Spalten im Rowset des Anbieters. Die Anbieter-Spalte-Zuordnung enthält einen Eintrag für jedes Feld in das Rowset mit die-Makros. Die Makros Geben Sie Spaltennamen, ordinal, und auf einen Struktureintrag der Offset. Die Einträge für den Anbieter im obigen Code enthalten, die Offsets in die `WIN32_FIND_DATA` Struktur. Wenn der Consumer ruft `IRowset::GetData`, Daten in einem zusammenhängenden Puffer übertragen werden. Anstatt zu sorgen, dass Sie die Zeigerarithmetik auszuführen, können mit die Zuordnung geben Sie einen Datenmember.

Die `CCustomRowset` Klasse enthält auch die `Execute` Methode. `Execute` ist tatsächlich, durch die Daten aus der systemeigenen Quelle eingelesen. Der folgende Code zeigt die vom Assistenten generierte `Execute` Methode. Die Funktion verwendet die Win32 `FindFirstFile` und `FindNextFile` APIs zum Abrufen von Informationen zu den Dateien im Verzeichnis, und fügen Sie sie in Instanzen von der `CCustomWindowsFile` Klasse.

```cpp
/////////////////////////////////////////////////////////////////////
// CustomRS.H

HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)
{
   USES_CONVERSION;
   BOOL bFound = FALSE;
   HANDLE hFile;
   LPTSTR  szDir = (m_strCommandText == _T("")) ? _T("*.*") :
       OLE2T(m_strCommandText);
   CCustomWindowsFile wf;
   hFile = FindFirstFile(szDir, &wf);
   if (hFile == INVALID_HANDLE_VALUE)
      return DB_E_ERRORSINCOMMAND;
   LONG cFiles = 1;
   BOOL bMoreFiles = TRUE;
   while (bMoreFiles)
   {
      if (!m_rgRowData.Add(wf))
         return E_OUTOFMEMORY;
      bMoreFiles = FindNextFile(hFile, &wf);
      cFiles++;
   }
   FindClose(hFile);
   if (pcRowsAffected != NULL)
      *pcRowsAffected = cFiles;
   return S_OK;
}
```

Das zu durchsuchende Verzeichnis zeigt `m_strCommandText`; enthält den Text, dargestellt durch die `ICommandText` -Schnittstelle in das Command-Objekt. Wenn kein Verzeichnis angegeben ist, wird das aktuelle Verzeichnis verwendet.

Die Methode erstellt einen Eintrag für jede Datei (entspricht einer Zeile) und platziert es in der `m_rgRowData` -Datenmember. Die `CRowsetImpl` -Klasse definiert die `m_rgRowData` -Datenmember. Die Daten in diesem Array werden die gesamte Tabelle angezeigt und werden in den Vorlagen verwendet.

## <a name="see-also"></a>Siehe auch

[Vom Anbieter-Assistenten generierte Dateien](../../data/oledb/provider-wizard-generated-files.md)<br/>
