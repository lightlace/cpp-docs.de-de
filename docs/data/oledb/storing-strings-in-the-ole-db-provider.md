---
title: Speichern von Zeichenfolgen im OLE DB-Anbieter
ms.date: 10/26/2018
helpviewer_keywords:
- user records, editing
ms.assetid: 36cb9635-067c-4cad-8f85-962f28026f6a
ms.openlocfilehash: 54dfdb347c621cf6f8645feb6d13742f32503f9f
ms.sourcegitcommit: 943c792fdabf01c98c31465f23949a829eab9aad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2018
ms.locfileid: "51264618"
---
# <a name="storing-strings-in-the-ole-db-provider"></a>Speichern von Zeichenfolgen im OLE DB-Anbieter

In *benutzerdefinierte*RS.h, die **ATL-OLE DB-Anbieter-Assistenten** erstellt ein Standard-Benutzer-Eintrag namens `CWindowsFile`. Ändern, um die beiden Zeichenfolgen zu behandeln, `CWindowsFile` wie im folgenden Code gezeigt:

```cpp
////////////////////////////////////////////////////////////////////////
class CCustomWindowsFile:
   public WIN32_FIND_DATA
{
public:
DWORD dwBookmark;
static const int iSize = 256;    // Add this
TCHAR szCommand[iSize];          // Add this
TCHAR szText[iSize];             // Add this
TCHAR szCommand2[iSize];         // Add this
TCHAR szText2[iSize];            // Add this

BEGIN_PROVIDER_COLUMN_MAP(CCustomWindowsFile)
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)

   PROVIDER_COLUMN_ENTRY_STR("Command", 6, szCommand)    // Add this
   PROVIDER_COLUMN_ENTRY_STR("Text", 7, szText)          // Add this
   PROVIDER_COLUMN_ENTRY_STR("Command2", 8, szCommand2)  // Add this
   PROVIDER_COLUMN_ENTRY_STR("Text2", 9, szText2)        // Add this
END_PROVIDER_COLUMN_MAP()

   bool operator==(const CCustomWindowsFile& am) // This is optional
   {
      return (lstrcmpi(cFileName, am.cFileName) == 0);
   }
};
```

Die Datenmember `szCommand` und `szText` darstellen von zwei Zeichenfolgen mit `szCommand2` und `szText2` mit zusätzlichen Spalten, die bei Bedarf. Das Datenelement `dwBookmark` für diesen einfachen schreibgeschützten Anbieters ist nicht erforderlich, aber später verwendet wird, um das Hinzufügen einer `IRowsetLocate` Schnittstelle; finden Sie unter [Erweitern des einfachen lesen nur Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md). Die `==` Operator vergleicht Instanzen (Implementierung dieses Operators ist optional).

Wenn dies abgeschlossen ist, können Sie die Funktionalität von hinzufügen [Einlesen von Zeichenfolgen in OLE DB-Anbieter](../../data/oledb/reading-strings-into-the-ole-db-provider.md).

## <a name="see-also"></a>Siehe auch

[Implementieren des einfachen schreibgeschützten Anbieters](../../data/oledb/implementing-the-simple-read-only-provider.md)<br/>
