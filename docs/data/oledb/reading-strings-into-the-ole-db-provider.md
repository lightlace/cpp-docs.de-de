---
title: Lesen von Zeichenfolgen in OLE DB-Anbieter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/13/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, reading strings into
ms.assetid: 517f322c-f37e-4eed-bf5e-dd9a412c2f98
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9b51611ff5727a89e47bef569865f915a189a993
ms.sourcegitcommit: db6b2ad3195e71abfb60b62f3f015f08b0a719d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2018
ms.locfileid: "49410654"
---
# <a name="reading-strings-into-the-ole-db-provider"></a>Einlesen von Zeichenfolgen in den OLE DB-Anbieter

Die `RMyProviderRowset::Execute` Funktion eine Datei öffnet und liest Zeichenfolgen. Der Consumer übergibt den Dateinamen an dem Anbieter an, durch den Aufruf [ICommandText:: SetCommandText](/previous-versions/windows/desktop/ms709757). Der Anbieter erhält den Dateinamen und speichert sie in der Membervariablen `m_szCommandText`. `Execute` liest den Dateinamen aus `m_szCommandText`. Wenn der Dateiname ungültig ist, oder die Datei nicht verfügbar ist ist, `Execute` gibt einen Fehler zurück. Sie geöffnet wird, andernfalls die Datei, und Aufrufe `fgets` die Zeichenfolgen ab. Für jede von Zeichenfolgen es liest, legen Sie `Execute` erstellt eine Instanz des Benutzerdatensatzes (`CAgentMan`) und setzt es in ein Array.  
  
Wenn die Datei kann nicht geöffnet werden, `Execute` DB_E_NOTABLE zurückgeben. Wenn sie stattdessen E_FAIL zurückgibt, wird der Anbieter funktioniert nicht mit vielen Consumern und der OLE DB wird nicht übergeben [Konformitätstests](../../data/oledb/testing-your-provider.md).  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  

Die bearbeitete `Execute` Funktion sieht wie folgt aus:  
  
### <a name="code"></a>Code  
  
```cpp
/////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
class RMyProviderRowset : public CRowsetImpl< RMyProviderRowset, CAgentMan, CRMyProviderCommand>  
{  
public:  
    HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)  
    {  
        enum {  
            sizeOfBuffer = 256,  
            sizeOfFile = MAX_PATH  
        };  
        USES_CONVERSION;  
        FILE* pFile = NULL;  
        TCHAR szString[sizeOfBuffer];  
        TCHAR szFile[sizeOfFile];  
        size_t nLength;        errcodeerr;  
  
        ObjectLock lock(this);  
  
        // From a filename, passed in as a command text, scan the file  
        // placing data in the data array.  
        if (!m_szCommandText)  
        {  
            ATLTRACE("No filename specified");  
            return E_FAIL;  
        }  
  
        // Open the file  
        _tcscpy_s(szFile, sizeOfFile, m_szCommandText);  
        if (szFile[0] == _T('\0') ||   
            ((err = fopen_s(&pFile, &szFile[0], "r")) == 0))  
        {  
            ATLTRACE("Could not open file");  
            return DB_E_NOTABLE;  
        }  
  
        // Scan and parse the file.  
        // The file should contain two strings per record  
        LONG cFiles = 0;  
        while (fgets(szString, sizeOfBuffer, pFile) != NULL)  
        {  
            nLength = strnlen(szString, sizeOfBuffer);  
            szString[nLength-1] = '\0';   // Strip off trailing CR/LF  
            CAgentMan am;  
            _tcscpy_s(am.szCommand, am.sizeOfCommand, szString);  
            _tcscpy_s(am.szCommand2, am.sizeOfCommand2, szString);  
  
            if (fgets(szString, sizeOfBuffer, pFile) != NULL)  
            {  
                nLength = strnlen(szString, sizeOfBuffer);  
                szString[nLength-1] = '\0'; // Strip off trailing CR/LF  
                _tcscpy_s(am.szText, am.sizeOfText, szString);  
                _tcscpy_s(am.szText2, am.sizeOfText2, szString);  
            }  
  
            am.dwBookmark = ++cFiles;  
            if (!m_rgRowData.Add(am))  
            {  
                ATLTRACE("Couldn't add data to array");  
                fclose(pFile);  
                return E_FAIL;  
            }  
        }  
  
        if (pcRowsAffected != NULL)  
            *pcRowsAffected = cFiles;  
        return S_OK;  
    }  
}  
```  
  
## <a name="see-also"></a>Siehe auch  

[Implementieren des einfachen schreibgeschützten Anbieters](../../data/oledb/implementing-the-simple-read-only-provider.md)