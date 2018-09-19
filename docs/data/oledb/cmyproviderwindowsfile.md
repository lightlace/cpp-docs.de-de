---
title: CMyProviderWindowsFile | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- cmyproviderwindowsfile
dev_langs:
- C++
helpviewer_keywords:
- CMyProviderWindowsFile class
- OLE DB providers, wizard-generated files
ms.assetid: 0e9e72ac-1e1e-445f-a7ac-690c20031f9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6f3badc08da7bd11e65c244c42c91ad37a584ca5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087265"
---
# <a name="cmyproviderwindowsfile"></a>CMyProviderWindowsFile

Der Assistent erstellt eine Klasse, um eine Zeile mit Daten enthalten. In diesem Fall heißt es `CMyProviderWindowsFile`. Der folgende code für `CMyProviderWindowsFile` Assistenten generiert wird, und listet alle Dateien in einem Verzeichnis mit dem `WIN32_FIND_DATA` Struktur. `CMyProviderWindowsFile` erbt von der `WIN32_FIND_DATA` Struktur:  
  
```cpp
/////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
  
class CMyProviderWindowsFile:   
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
  
`CMyProviderWindowsFile` wird aufgerufen, die [Benutzerdatensatz-Klasse](../../data/oledb/user-record.md) , da es enthält auch eine Zuordnung, die Beschreibung der Spalten im Rowset des Anbieters. Die Anbieter-Spalte-Zuordnung enthält einen Eintrag für jedes Feld in das Rowset mit die-Makros. Die Makros Geben Sie Spaltennamen, ordinal, und auf einen Struktureintrag der Offset. Die Einträge für den Anbieter im obigen Code enthalten, die Offsets in die `WIN32_FIND_DATA` Struktur. Wenn der Consumer ruft `IRowset::GetData`, Daten in einem zusammenhängenden Puffer übertragen werden. Anstatt zu sorgen, dass Sie die Zeigerarithmetik auszuführen, können mit die Zuordnung geben Sie einen Datenmember.  
  
Die `CMyProviderRowset` Klasse enthält auch die `Execute` Methode. `Execute` ist tatsächlich, durch die Daten aus der systemeigenen Quelle eingelesen. Der folgende Code zeigt die vom Assistenten generierte `Execute` Methode. Die Funktion verwendet die Win32 `FindFirstFile` und `FindNextFile` APIs zum Abrufen von Informationen zu den Dateien im Verzeichnis, und fügen Sie sie in Instanzen von der `CMyProviderWindowsFile` Klasse.  
  
```cpp
/////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
  
HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)  
{  
   USES_CONVERSION;  
   BOOL bFound = FALSE;  
   HANDLE hFile;  
   LPTSTR  szDir = (m_strCommandText == _T("")) ? _T("*.*") :  
       OLE2T(m_strCommandText);  
   CMyProviderWindowsFile wf;  
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
  
Das zu durchsuchende Verzeichnis wird durch dargestellt `m_strCommandText`; enthält den Text, der durch dargestellt die `ICommandText` -Schnittstelle in das Command-Objekt. Wenn kein Verzeichnis angegeben ist, wird das aktuelle Verzeichnis verwendet.  
  
Die Methode erstellt einen Eintrag für jede Datei (entspricht einer Zeile) und platziert es in der `m_rgRowData` -Datenmember. Die `CRowsetImpl` -Klasse definiert die `m_rgRowData` -Datenmember. Die Daten in diesem Array stellt die gesamte Tabelle dar und werden in den Vorlagen verwendet.  
  
## <a name="see-also"></a>Siehe auch  

[Vom Anbieter-Assistenten generierte Dateien](../../data/oledb/provider-wizard-generated-files.md)