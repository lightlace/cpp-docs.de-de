---
title: "Einlesen von Zeichenfolgen in den OLE&#160;DB-Anbieter | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB-Anbieter, Einlesen von Zeichenfolgen in"
ms.assetid: 517f322c-f37e-4eed-bf5e-dd9a412c2f98
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Einlesen von Zeichenfolgen in den OLE&#160;DB-Anbieter
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `RMyProviderRowset::Execute`\-Funktion öffnet eine Datei und liest Zeichenfolgen ein.  Der Consumer übergibt den Dateinamen durch Aufruf von [ICommandText::SetCommandText](https://msdn.microsoft.com/en-us/library/ms709757.aspx) an den Anbieter.  Der Anbieter empfängt den Dateinamen und speichert ihn in der Membervariable `m_szCommandText`.  `Execute` liest den Dateinamen aus `m_szCommandText`.  Falls der Dateiname ungültig oder die Datei nicht verfügbar ist, gibt `Execute` einen Fehler zurück.  Andernfalls wird die Datei geöffnet und `fgets` aufgerufen, um die Zeichenfolgen abzurufen.  Für jedes gelesene Zeichenfolgenset wird von `Execute` eine Instanz des Benutzerdatensatzes \(`CAgentMan`\) erstellt und in ein Array eingefügt.  
  
 Falls die Datei nicht geöffnet werden kann, muss `Execute` **DB\_E\_NOTABLE** zurückgeben.  Wenn stattdessen **E\_FAIL** zurückgegeben wird, funktioniert der Anbieter nicht mit zahlreichen Consumern und besteht die OLE DB\-[Konformitätstests](../../data/oledb/testing-your-provider.md) nicht.  
  
## Beispiel  
  
### **Beschreibung**  
 Die bearbeitete `Execute`\-Funktion sieht wie folgt aus:  
  
### Code  
  
```  
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
  
## Siehe auch  
 [Implementieren des einfachen schreibgeschützten Anbieters](../../data/oledb/implementing-the-simple-read-only-provider.md)