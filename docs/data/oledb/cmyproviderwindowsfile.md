---
title: CMyProviderWindowsFile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cmyproviderwindowsfile
dev_langs:
- C++
helpviewer_keywords:
- CMyProviderWindowsFile class
- OLE DB providers, wizard-generated files
ms.assetid: 0e9e72ac-1e1e-445f-a7ac-690c20031f9d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5f9549dc81529f4c045a0f27a169516070a09900
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cmyproviderwindowsfile"></a>CMyProviderWindowsFile
Der Assistent erstellt eine Klasse, um eine Zeile mit Daten enthalten. In diesem Fall heißt es `CMyProviderWindowsFile`. Der folgende code für `CMyProviderWindowsFile` Assistenten generiert wird, und listet alle Dateien in einem Verzeichnis mithilfe der **WIN32_FIND_DATA** Struktur. `CMyProviderWindowsFile` erbt von der **WIN32_FIND_DATA** Struktur:  
  
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
  
 `CMyProviderWindowsFile` wird aufgerufen, die [Benutzerdatensatz-Klasse](../../data/oledb/user-record.md) , da es enthält auch eine Zuordnung, die Beschreibung der Spalten im Rowset des Anbieters. Die Anbieter-Spalte-Zuordnung enthält einen Eintrag für jedes Feld in das Rowset mit der-Makros. Die Makros Geben Sie Spaltennamen, ordinal, und das Offset für einen Struktureintrag. Der Anbieterspalteneinträge in den oben aufgeführten Code enthalten Offsets in die **WIN32_FIND_DATA** Struktur. Wenn der Consumer ruft **IRowset:: GetData**, Daten in einem zusammenhängenden Puffer übertragen. Statt Zeigerarithmetik möglich ist, können mit die Zuordnung geben Sie einen Datenmember.  
  
 Die `CMyProviderRowset` Klasse enthält auch die `Execute` Methode. `Execute` ist, was tatsächlich die Daten in der systemeigenen-Quelle liest. Der folgende Code zeigt die vom Assistenten generierten `Execute` Methode. Die Funktion verwendet die Win32 **FindFirstFile** und `FindNextFile` APIs zum Abrufen von Informationen zu den Dateien im Verzeichnis, und fügen Sie sie in Instanzen von der `CMyProviderWindowsFile` Klasse.  
  
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
  
 Zu durchsuchenden Verzeichnisses dargestellte `m_strCommandText`; dieses enthält den Text, dargestellt durch die `ICommandText` -Schnittstelle in das Command-Objekt. Wenn kein Verzeichnis angegeben ist, verwendet es das aktuelle Verzeichnis.  
  
 Die Methode erstellt einen Eintrag für jede Datei (Dies entspricht einer Zeile) und platziert es in der **M_rgRowData** -Datenmember. Die `CRowsetImpl` Klasse definiert die **M_rgRowData** -Datenmember. Die Daten in dieses Array stellt die gesamte Tabelle dar und werden in den Vorlagen verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Vom Anbieter-Assistenten generierte Dateien](../../data/oledb/provider-wizard-generated-files.md)