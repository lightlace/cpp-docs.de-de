---
title: Einlesen von Zeichenfolgen in den OLE DB-Anbieter
ms.date: 10/13/2018
helpviewer_keywords:
- OLE DB providers, reading strings into
ms.assetid: 517f322c-f37e-4eed-bf5e-dd9a412c2f98
ms.openlocfilehash: d46b4e1a53e7e489763f40e7a5238e65b493f7c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62283809"
---
# <a name="reading-strings-into-the-ole-db-provider"></a>Einlesen von Zeichenfolgen in den OLE DB-Anbieter

Die `CCustomRowset::Execute` Funktion eine Datei öffnet und liest Zeichenfolgen. Der Consumer übergibt den Dateinamen an dem Anbieter an, durch den Aufruf [ICommandText:: SetCommandText](/previous-versions/windows/desktop/ms709757(v=vs.85)). Der Anbieter erhält den Dateinamen und speichert sie in der Membervariablen `m_strCommandText`. `Execute` liest den Dateinamen aus `m_strCommandText`. Wenn der Dateiname ungültig ist, oder die Datei nicht verfügbar ist ist, `Execute` gibt einen Fehler zurück. Sie geöffnet wird, andernfalls die Datei, und Aufrufe `fgets` die Zeichenfolgen ab. Für jede von Zeichenfolgen es liest, legen Sie `Execute` erstellt eine Instanz des Benutzerdatensatzes (geändert `CCustomWindowsFile` aus [Speichern von Zeichenfolgen im OLE DB-Anbieter](../../data/oledb/storing-strings-in-the-ole-db-provider.md)) und setzt es in ein Array.

Wenn die Datei kann nicht geöffnet werden, `Execute` DB_E_NOTABLE zurückgeben. Wenn sie stattdessen E_FAIL zurückgibt, wird der Anbieter funktioniert nicht mit vielen Consumern und übergeben Sie den OLE DB wird nicht [Konformitätstests](../../data/oledb/testing-your-provider.md).

## <a name="example"></a>Beispiel

```cpp
/////////////////////////////////////////////////////////////////////////
// CustomRS.h
class CCustomRowset : public CRowsetImpl< CCustomRowset, CCustomWindowsFile, CCustomCommand>
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
        size_t nLength;

        ObjectLock lock(this);

        // From a filename, passed in as a command text, scan the file
        // placing data in the data array.
        if (!m_strCommandText)
        {
            ATLTRACE("No filename specified");
            return E_FAIL;
        }

        // Open the file
        _tcscpy_s(szFile, sizeOfFile, m_strCommandText);
        if (szFile[0] == _T('\0') ||
            (fopen_s(&pFile, (char*)&szFile[0], "r") == 0))
        {
            ATLTRACE("Could not open file");
            return DB_E_NOTABLE;
        }

        // Scan and parse the file.
        // The file should contain two strings per record
        LONG cFiles = 0;
        while (fgets((char*)szString, sizeOfBuffer, pFile) != NULL)
        {
            nLength = strnlen((char*)szString, sizeOfBuffer);
            szString[nLength-1] = '\0';   // Strip off trailing CR/LF
            CCustomWindowsFile am;
            _tcscpy_s(am.szCommand, am.iSize, szString);
            _tcscpy_s(am.szCommand2, am.iSize, szString);

            if (fgets((char*)szString, sizeOfBuffer, pFile) != NULL)
            {
                nLength = strnlen((char*)szString, sizeOfBuffer);
                szString[nLength-1] = '\0'; // Strip off trailing CR/LF
                _tcscpy_s(am.szText, am.iSize, szString);
                _tcscpy_s(am.szText2, am.iSize, szString);
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
};
```

Wenn dies abgeschlossen ist, sollte Ihr Anbieter bereit sein zu kompilieren und auszuführen. Um den Anbieter zu testen, benötigen Sie einen Consumer mit übereinstimmenden Funktionen. [Implementieren eines einfachen Consumers](../../data/oledb/implementing-a-simple-consumer.md) zeigt, wie solche einen Testconsumer erstellen. Führen Sie den Testconsumer mit dem Anbieter aus, und stellen Sie sicher, dass der Testconsumer die richtigen Zeichenfolgen vom Anbieter empfängt.

Wenn Sie Ihren Anbieter erfolgreich getestet haben, empfiehlt es sich um die Funktionalität zu verbessern, indem Sie die Implementierung zusätzlicher Schnittstellen. Ein Beispiel ist in [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md).

## <a name="see-also"></a>Siehe auch

[Implementieren des einfachen schreibgeschützten Anbieters](../../data/oledb/implementing-the-simple-read-only-provider.md)<br/>
