---
title: "CMyProviderWindowsFile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cmyproviderwindowsfile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMyProviderWindowsFile-Klasse"
  - "OLE DB-Anbieter, Assistentengenerierte Dateien"
ms.assetid: 0e9e72ac-1e1e-445f-a7ac-690c20031f9d
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CMyProviderWindowsFile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Assistent erstellt eine Klasse für eine Datenzeile, die in diesem Fall `CMyProviderWindowsFile` genannt wird.  Der folgende Code für `CMyProviderWindowsFile` wird vom Assistenten generiert. Darin werden mithilfe der **WIN32\_FIND\_DATA**\-Struktur alle in einem Verzeichnis enthaltenen Dateien aufgelistet.  `CMyProviderWindowsFile` erbt von der **WIN32\_FIND\_DATA**\-Struktur:  
  
```  
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
  
 `CMyProviderWindowsFile` wird als [Benutzerdatensatz\-Klasse](../../data/oledb/user-record.md) bezeichnet, da die Datei zusätzlich eine Zuordnung enthält, in der die im Anbieterrowset enthaltenen Spalten beschrieben sind.  Die Anbieterspaltenzuordnung enthält einen Eintrag für jedes Feld im Rowset, das `PROVIDER_COLUMN_ENTRY`\-Makros verwendet.  Die Makros legen den Spaltennamen, die Ordnungszahl und das Offset für einen Struktureintrag fest.  Die Anbieterspalteneinträge im oben aufgeführten Code enthalten Offsets in die **WIN32\_FIND\_DATA**\-Struktur.  Wenn der Consumer **IRowset::GetData** aufruft, werden die Daten in einem zusammenhängenden Puffer übertragen.  Da die Zuordnung die Möglichkeit bietet, einen Datenmember festzulegen, müssen Sie nicht auf die Zeigerarithmetik zurückgreifen.  
  
 Die `CMyProviderRowset`\-Klasse enthält darüber hinaus die `Execute`\-Methode.  `Execute` ist die Methode, durch die Daten aus der systemeigenen Quelle eingelesen werden.  Im folgenden Code ist die vom Assistenten generierte `Execute`\-Methode zu sehen.  Die Funktion verwendet die APIs **FindFirstFile** und `FindNextFile`, um Informationen über die Dateien abzurufen und sie in Instanzen der `CMyProviderWindowsFile`\-Klasse einzufügen.  
  
```  
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
  
 Das zu durchsuchende Verzeichnis wird durch `m_strCommandText` angegeben. Darin ist der Text enthalten, der durch die `ICommandText`\-Schnittstelle im Befehlsobjekt dargestellt wird.  Falls kein Verzeichnis angegeben ist, wird das aktuelle Verzeichnis verwendet.  
  
 Die Methode erstellt einen Eintrag \(von einer Zeile\) für jede Datei und fügt ihn in den **m\_rgRowData**\-Datenmember ein.  Der **m\_rgRowData**\-Datenmember wird durch die `CRowsetImpl`\-Klasse definiert.  Die Daten in diesem Array bilden die gesamte Tabelle und werden übergreifend für alle Vorlagen verwendet.  
  
## Siehe auch  
 [Vom Anbieter\-Assistenten generierte Dateien](../../data/oledb/provider-wizard-generated-files.md)