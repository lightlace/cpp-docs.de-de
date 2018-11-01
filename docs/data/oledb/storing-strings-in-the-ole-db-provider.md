---
title: Speichern von Zeichenfolgen im OLE DB-Anbieter
ms.date: 10/26/2018
helpviewer_keywords:
- user records, editing
ms.assetid: 36cb9635-067c-4cad-8f85-962f28026f6a
ms.openlocfilehash: b1bc7ca74ce114f9d901fc5771a376df973f54a8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50652334"
---
# <a name="storing-strings-in-the-ole-db-provider"></a>Speichern von Zeichenfolgen im OLE DB-Anbieter

In der Datei MyProviderRS.h der **ATL-OLE DB-Anbieter-Assistenten** erstellt ein Standard-Benutzer-Eintrag namens `CWindowsFile`. Um die beiden Zeichenfolgen zu behandeln, ändern Sie entweder `CWindowsFile` oder Ihre eigenen Benutzerdatensatz hinzufügen, wie im folgenden Code gezeigt:

```cpp
////////////////////////////////////////////////////////////////////////
class CAgentMan: 
   public WIN32_FIND_DATA
   DWORD dwBookmark;              // Add this
   TCHAR szCommand[256];          // Add this
   TCHAR szText[256];             // Add this
   TCHAR szCommand2[256];         // Add this
   TCHAR szText2[256];            // Add this
  
{
public:
BEGIN_PROVIDER_COLUMN_MAP()
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Command"), 1, 256, GUID_NULL, CAgentMan, szCommand)
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Text"), 2, 256, GUID_NULL, CAgentMan, szText) 
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Command2"), 3, 256, GUID_NULL, CAgentMan, szCommand2)
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Text2"),4, 256, GUID_NULL, CAgentMan, szText2)
END_PROVIDER_COLUMN_MAP()
   bool operator==(const CAgentMan& am) // This is optional 
   {
      return (lstrcmpi(cFileName, wf.cFileName) == 0);
   }
};
```

Die Datenmember `szCommand` und `szText` darstellen von zwei Zeichenfolgen mit `szCommand2` und `szText2` mit zusätzlichen Spalten, die bei Bedarf. Das Datenelement `dwBookmark` für diesen einfachen schreibgeschützten Anbieters ist nicht erforderlich, aber später verwendet wird, um das Hinzufügen einer `IRowsetLocate` Schnittstelle; finden Sie unter [Erweitern des einfachen lesen nur Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md). Die `==` Operator vergleicht Instanzen (Implementierung dieses Operators ist optional).

Wenn dies abgeschlossen ist, sollte Ihr Anbieter bereit sein zu kompilieren und auszuführen. Um den Anbieter zu testen, benötigen Sie einen Consumer mit übereinstimmenden Funktionen. [Implementieren eines einfachen Consumers](../../data/oledb/implementing-a-simple-consumer.md) zeigt, wie solche einen Testconsumer erstellen. Führen Sie den Testconsumer mit dem Anbieter ein. Stellen Sie sicher, dass der Testconsumer Ruft die richtigen Zeichenfolgen vom Anbieter ab, wenn Sie auf die **ausführen** Schaltfläche der **Testconsumer** Dialogfeld.

Wenn Sie Ihren Anbieter erfolgreich getestet haben, empfiehlt es sich um die Funktionalität zu verbessern, indem Sie die Implementierung zusätzlicher Schnittstellen. Ein Beispiel ist in [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md).

## <a name="see-also"></a>Siehe auch

[Implementieren des einfachen schreibgeschützten Anbieters](../../data/oledb/implementing-the-simple-read-only-provider.md)<br/>
